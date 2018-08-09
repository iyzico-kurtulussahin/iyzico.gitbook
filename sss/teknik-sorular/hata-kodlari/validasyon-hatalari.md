---
description: 'iyzico API''ı tarafından, işlem bankaya gönderilmeden verilen hatalardır.'
---

# Validasyon Hataları

### 3 - email gönderilmesi zorunludur

 Ödeme isteğinde iyzico API'ına gönderilen buyerEmail parametresi zorunlu bir parametredir. Eğer bu parametre gönderilmemiş ise iyizco API'ından _**email gönderilmesi zorunludur**_ mesajı dönmektedir.

### 8 - identityNumber gönderilmesi zorunludur

iyzico API'ında identityNumber parametresi ile kimlik numarasının gönderilmesi MASAK mevzuatı gereğince tüm müşterilerimiz için zorunludur. Bu parametre gönderilmediğinde "identityNumber gönderilmesi zorunludur" hata mesajı dönecektir. 

**Suç Gelirlerinin Aklanmasının ve Terörün Finansmanının Önlenmesine Dair Tedbirler Hakkında Yönetmelik:**

 **Madde 6:** Gerçek kişilerin kimlik tespitinde; ilgilinin adı, soyadı, doğum yeri ve tarihi, uyruğu, kimlik belgesinin türü ve numarası, adresi ve imza örneği, varsa telefon numarası, faks numarası, elektronik posta adresi, iş ve mesleğine ilişkin bilgiler ile Türk vatandaşları için bu bilgilere ilave olarak anne, baba adı ve T.C. kimlik numarası alınır.

 **Madde 7:**  Ticaret siciline kayıtlı tüzel kişilerin kimlik tespitinde; tüzel kişinin unvanı, ticaret sicil numarası, vergi kimlik numarası, faaliyet konusu, açık adresi, telefon numarası, varsa faks numarası ve elektronik posta adresi ile tüzel kişiliği temsile yetkili kişinin adı, soyadı, doğum yeri ve tarihi, uyruğu, kimlik belgesinin türü ve numarasına ilişkin bilgiler ve imza örneği ile Türk vatandaşları için bu bilgilere ilave olarak anne, baba adı ve T.C. kimlik numarası alınır.

### 12 - Kart numarası geçersizdir

Bu hata kart numarası “luhn” algoritmasına uygun olmadığında dönmektedir.

Kart numarası yanlış girilmiş olabilir, içinde harf veya boşluk bulunuyor olabilir.   
Eğer kart numarası iyzico'ya gönderilmeden önce "luhn" algoritması kontrolü yapılırsa bu hata alınmayacaktır.

### 1000 - Geçersiz imza

iyzico API’ına datalar gönderilirken güvenlik amaçlı olarak şifrelenip bir hash ile iletilmektedir. Eğer bu hash iyzico tarafında çözülemez ise bu hata mesajı dönmektedir.

Bu hataya sebep olan durumlar: 

1. Güvenlik anahtarının \(secret key\) yanlış girilmesi
2. Utf8 kullanılmaması
3. Parametrelerin uygun formatta gönderilmemesi



1. **Senaryo kontrolü :** Aynı ortamda en basit sorgu olan bin sorgusu yaparak bir deneme yapabilirsiniz.
2. **Senaryo kontrolü :** Eğer sorgu başarılı olursa,  conversationId parametresine türkçe karakterler ekleyerek deneyebilirsiniz.
3. **Senaryo kontrolü :** Githubdaki örneğimizdeki parametreleri birebir set ederek bir deneme yaparak kontrol edebilirsinz.

### 1001 - Api bilgileri bulunamadı

"Api bilgileri bulunamadı" hata mesayı eğer api anahtarınız iyzico'nun sorgu yaptığınız ortamında \(sandbox veya live\) kayıtlı değil ise alınmaktadır. 

İlk olarak api anahtarınızı doğru girdiğinizi kontrol edebilirsiniz. Api anahtarlarınızı doğru girdiğinizden emin iseniz, sorgu yapılan ortam baseUrl değerini kontrol etmelisiniz. resmi/canlı hesabınızın api anahtarları ile sandbox ortamına sorgu yapıyorsanız veya tam tersi, sandbox ortamına air anahtarlar ile canlı ortama sorgu yapıyorsanız "Api bilgileri bulunamadı" hatası dönecektir. 

Canlı ortama sorgu yaparken baseUrl değeri:

```bash
https://api.iyzipay.com
```

Sandbox ortamına sorgu yaparken baseUrl değeri:

```text
https://sandbox-api.iyzipay.com
```

### 5062 - Gönderilen tutar tüm kırılımların toplam tutarına eşit olmalıdır

Ödeme isteğinde veya ödeme formu başlatma isteğinde, iyzico API’ına 3 temel fiyat bilgisi gönderilmektedir. 

* paidPrice : karttan çekilecek tutar
* price: sepettteki ürünlerin toplam tutarı 
* basketItemPrice : sepetteki her bir ürün için fiyat bilgisi

Sepetteki ürünlerin toplam fiyatı _**price**_ parametresindeki tutara eşit olmalıdır. _**price**_ parametresinin itemPrice’lar toplamına eşit olmadığı durumda bu hata dönmektedir. 

### 5079 - Marketplace üye işyeri için sadece ürün ödemesi yapılırken subMerchantKey veya subMerchantPrice gönderilmelidir

Marketplace hesabında ödeme isteğinde PaymentGroup parametresini _`PRODUCT`_ olarak set edilmemiş ise, _`LISTING`_ veya _`SUBSCRIPTION`_ olarak set edilmiş ise subMerchantKey ve subMerchantPrice parametreleri gönderilmemelidir. Bu senaryoda çekilen tutar tamamiyle platform hesabına aktarılmaktadır.

### 5184 - Yerli kartlar ile döviz ödemesi yapılamaz

Türk lirasını koruma konunu gereği Türk poslarından Türk kartları ile işlem yapılacaksa yalnızca Türk lirası kullanılabilir. iyzico Türk bankalarına ait posları kulanmaktadır ve bu bankalar, Türk kartından bir işlem döviz olarak gelirse "Türk Lirasını Koruma Kanunu" gereği reddetmektedir. Bu sebeple sistemimiz, Türk kartları ile döviz işlemi yapılmaya çalışılırsa "Yerli karlarla döviz ödemesi yapılamaz" hata mesajı dönmektedir.

### 9000 - Şu anda işleminizi gerçekleştiremiyoruz. Detaylı bilgi için iyzico ile iletişime geçiniz

Hesabınız iyzico ekibi tarafından geçici olarak dondurulmuştur, iyzico yardım merkezinden iletişime geçerek ayrıntılı bilgi alabilir, hesabınızın aktif edilmesini sağlayabilirsiniz.

{% embed data="{\"url\":\"https://www.iyzico.com/iletisim\",\"type\":\"link\",\"title\":\"Yardım Merkezi  - iyzico.com\",\"icon\":{\"type\":\"icon\",\"url\":\"https://media.iyzico.com/f/assets/images/content/favicon.ico?v=v2.0.39\",\"aspectRatio\":0}}" %}

