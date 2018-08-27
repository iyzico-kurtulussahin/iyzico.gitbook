---
description: >-
  iyzico'nun ödeme formunu veya API'sini entegre etmek için gerekli kodlara
  buradan ulaşabilirsiniz.
---

# Yazılım bilgisi gerekli

iyzico ödeme API’si, internet üzerinden ödeme kabul eden tüm üye işyerlerine ihtiyacına cevap verecek şekilde, oturum bilgisi tutmayan \(stateless\) Restful servis odaklı bir mimaride geliştirilmiştir. iyzico'nun sunduğu sunucu taraflı programlama diline uygun istemciler \(client\) ile çok kolay entegre olunabilir. 

### Base Url

{% hint style="danger" %}
iyzico'da 2 farklı ortam bulunmaktadır. Canlı \(Live\) ortam ve Sandbox Test ortamı. Canlı ortam kontrol panelinizden erişebileceğiniz api anahtarları ile sandbox kontrol panelinizden erişebileceğiniz sandbox api anahtarları için kullanmanız gereken baseUrl değeri aşağıdaki gibi olmalıdır.

Canlı \(Live\) Ortam Api Anahtarları İçin : **`https://api.iyzipay.com`**

Sandbox Test Ortamı Api Anahtarları İçin :**`https://sandbox-api.iyzipay.com`**

Sandbox api anahtarlarına ulaşmak için [**https://sandbox-merchant.iyzipay.com/auth/register**](https://sandbox-merchant.iyzipay.com/auth/register) ****adresinden rastgele mail adresi kayıt oluşturup panelin "Ayarlar" bölümünden ulaşabilirsiniz.
{% endhint %}

### **iyzico github Sayfası**

{% page-ref page="../sss/teknik-sorular/github.com-iyzico.md" %}

### Sandbox \(Test\) Ortamı

{% page-ref page="../sss/teknik-sorular/sandbox-test-ortami.md" %}

### İyzico ödeme formu entegrasyonu

{% page-ref page="odeme-formu/" %}

### **Entegrasyon sürecinde dikkat edilecek noktalar**

* Canlı ortamda iyzico API'ına gönderilen parametrelere müşteriden alınan bilgiler set edilmelidir. Müşteriniden alınmayan "dummy" değerler sorgu parametrelerine set edilmemelidir.
* Ödeme işlemi sonucunda iyzico tarafından dönen cevaptaki değerler \(price, paidPrice, basketId, conversationId\) ile sizin sisteminize kaydettiğiniz değerleri karşılaştırarak bir farklılık var ise genel bir hata mesajı gösterebilirsiniz. Bu tür durumlarda iyzico entegrasyon ekibi ile iletişime geçmeyi unutmayınız. Müşteri tarafından ödenen tutar iyzico tarafından dönen cevaptaki paidPrice parametresindeki değere eşittir.

### **Canlı ortama geçiş**

* Geliştirmeler tamamlandıktan sonra ödeme adımlarınızı, test kartlarınız ile tüm durumlar için test edin.
* iyzico servislerinden dönen ve olabilecek tüm hataları karşılayacak şekilde kodunuzu düzenleyin.
* Sonuç sayfanızın iyzico'dan gelen yanıtı yorumlayabiliyor olmasına dikkat edin.
* Hassas olmayan dataları ve yanıtları loglamaya dikkat edin.
* Entegrasyonunuzun son kullanıcılar için [Kişisel Verilerin Koruması Kanunu](https://dev.iyzipay.com/tr/sss) ile uyumlu olmasına dikkat edin.
* iyzico logolarını sitenize eklemeyi unutmayın. [iyzico logo paketi](https://dev.iyzipay.com/tr/iyzico-logo-pack.zip).
* iyzico entegrasyon ekibinin onayı için [**entegrasyon@iyzico.com**](mailto:entegrasyon@iyzico.com) mail adresi ile iletişime geçin.

