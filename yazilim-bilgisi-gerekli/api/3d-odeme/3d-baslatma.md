---
description: >-
  Bankadan 3ds şifresi girilecek ekran'ı çağırmak için kullanılır. 2. Adım olan 
  "3d tamamlama" sorgusu yapılmadan karttan tutar çekilmez.
---

# 3d Başlatma

### 3ds Akışı

{% hint style="info" %}
Aşağıda belirtilen parametrelerle bir 3ds başlatma isteği yapıldığında, dönen cevap içerisindeki _**`threedsHtmlContent`**_ parametresinde, kullanıcıyı kart bankasının 3ds güvenlik ekranına  yönlendirecek script bulunur. 

Bu script tamamen banka tarafından iletilmektedir ve iyzico tarafından hiçbir müdahalede bulunulmamaktadır. 

Bu scripti, kart sahibinin gördüğü ekrana ilettiğiniz anda, tarayıcı kart sahibini, bankasının 3ds güvenlik ekranına yönlendirecek ve bu sayfada kart sahibi ile kart bankası başbaşa olacaktır.

Kart sahibi 3ds güvenlik şifresini girdikten sonra otomatik olarak callbackUrl parametresinde belirttiğiniz adrese yönlenecek ve iyzico bu adrese [**"CallbackUrl adresine post edilen değerler"**](https://iyzico.gitbook.io/tr/yazilim-bilgisi-gerekli/api/untitled/3d-baslatma#callbackurl-adresine-post-edilen-degerler) ****başlığında belirtilen parametreleri post edecektir.
{% endhint %}

{% embed data="{\"url\":\"https://github.com/iyzico/iyzipay-php/blob/master/samples/initialize\_threeds.php\#L1\",\"type\":\"link\",\"title\":\"iyzico/iyzipay-php\",\"description\":\"iyzipay-php - iyzipay api php client\",\"icon\":{\"type\":\"icon\",\"url\":\"https://github.com/fluidicon.png\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://avatars2.githubusercontent.com/u/3815564?s=400&v=4\",\"width\":200,\"height\":200,\"aspectRatio\":1},\"caption\":\"3d başlatma sorgusu Php örneği\"}" %}

### Parametreler

{% tabs %}
{% tab title="İstek Parametreleri" %}


| **Parametre İsmi** | **Tip** | **Zorunlu** | **Açıklama** |
| :--- | :--- | :--- | :--- |
| **locale** | String | Hayır | iyzico istek snucunda dönen metinlerin dilini ayarlamak için kullanılır. Varsayılan değeri tr’dir. **en** kullanılabilir. |
| **conversationId** | String | Hayır | İstek esnasında gönderip, sonuçta alabileceğiniz bir değer; request/response eşleşmesi yapmak için kullanılabilir. En yaygın kullanış biçimi üye işyerinin sipariş numarasıdır. |
| **price** | Decimal | Evet | Ödeme sepet tutarı. Kırılım \(sepetin içerisindeki ürünler\) tutarlar toplamı, sepet tutarına eşit olmalı. |
| **paidPrice** | Decimal | Evet | İndirim vade farkı vs. hesaplanmış POS’tan geçecek nihai tutar. Price değerinden küçük, büyük veya eşit olabilir. |
| **currency** | String | Evet | Ödemenin alınacağı para birimi default olarak TRY olarak belirlenmiştir. Diğer değerler ise USD, EUR ve GBP. |
| **installment** | Integer | Evet | Taksit bilgisi, tek çekim için 1 gönderilmelidir. Geçerli değerler: **1**, **2**, **3**, **6**, **9**. |
| **basketId** | String | Hayır | Üye işyeri tarafından ilgili ödemenin sepetini tanımlamak için kullanılan id'dir. Sipariş numarası veya anlamlı bir değer olabilir. |
| **paymentChannel** | String | Hayır | Ödeme kanalı. Geçerli değerler enum içinde sunulmaktadır: WEB, MOBILE, MOBILE\_WEB, MOBILE\_IOS, MOBILE\_ANDROID, MOBILE\_WINDOWS, MOBILE\_TABLET, MOBILE\_PHONE |
| **paymentGroup** | String | Hayır | Ödeme grubu, varsayılan PRODUCT. Geçerli değerler enum içinde sunulmaktadır: **PRODUCT**, **LISTING**, **SUBSCRIPTION**, **OTHER** |
| **callbackUrl** | String | Evet | 3D Secure ödeme akışında üye işyerine başarılı ve hatalı sonucu bildirmek üzere alınan URL adresi. Sadece 3D Secure ödemenin init3DS metodunda zorunludur. |
| **cardNumber** | String | Evet | Ödemenin alınacağı kart numarası. Eğer saklı kart ile ödeme yapılmıyorsa zorunludur. |
| **expireYear** | String | Evet | Ödemenin alınacağı kartın son kullanma tarihi yılı. Eğer saklı kart ile ödeme yapılmıyorsa zorunludur. |
| **expireMonth** | String | Evet | Ödemenin alınacağı kartın son kullanma tarihi ayı. Eğer saklı kart ile ödeme yapılmıyorsa zorunludur. |
| **cvc** | String | Evet | Ödemenin alınacağı kartın güvenlik kodu. Eğer saklı kart ile ödeme yapılmıyorsa zorunludur. Saklı kartla ödeme yapılırken gönderilirse aynen bankaya iletilir. |
| **cardHolderName** | String | Evet | Ödemenin alınacağı kart sahibinin adı soyadı. Eğer saklı kart ile ödeme yapılmıyorsa zorunludur. |
| **registerCard** | Integer | Hayır | Ödeme esnasında kartın kaydedilip kaydedilmeyeceğini belirleyen parametre. Varsayılan değeri 0 olup, geçerli değerler 0 ve 1’dir. |
| **id\(Buyer\)** | String | Evet | Üye işyeri tarafındaki alıcıya ait id. |
| **name\(Buyer\)** | String | Evet | Üye işyeri tarafındaki alıcıya ait ad. |
| **surname\(Buyer\)** | String | Evet | Üye işyeri tarafındaki alıcıya ait soyad. |
| **identityNumber\(Buyer\)** | String | Evet | Üye işyeri tarafındaki alıcıya ait kimlik \(TCKN\) numarası. |
| **city\(Buyer\)** | String | Evet | Üye işyeri tarafındaki alıcıya ait şehir bilgisi. |
| **country\(Buyer\)** | String | Evet | Üye işyeri tarafındaki alıcıya ait ülke bilgisi. |
| **email\(Buyer\)** | String | Evet | Üye işyeri tarafındaki alıcıya ait e-posta bilgisi. E-posta adresi alıcıya ait geçerli ve erişilebilir bir adres olmalıdır. |
| **gsmNumber\(Buyer\)** | String | Hayır | Üye işyeri tarafındaki alıcıya ait GSM numarası. |
| **ip\(Buyer\)** | String | Evet | Üye işyeri tarafındaki alıcıya ait IP adresi. |
| **registrationAddress\(Buyer\)** | String | Evet | Üye işyeri tarafındaki alıcıya ait kayıt adresi. |
| **zipCode\(Buyer\)** | String | Hayır | Üye işyeri tarafındaki alıcıya ait posta kodu. |
| **registrationDate\(Buyer\)** | String | Hayır | Üye işyeri tarafındaki alıcıya ait kayıt tarihi. Tarih formatı 2015-09-17 23:45:06 şeklinde olmalıdır. |
| **lastLoginDate\(Buyer\)** | String | Hayır | Üye işyeri tarafındaki alıcıya ait son giriş tarihi. Tarih formatı 2015-09-17 23:45:06 şeklinde olmalıdır. |
| **contactName\(BillingAddress\)** | String | Evet | Üye işyeri tarafındaki fatura adresi ad soyad bilgisi. |
| **city\(BillingAddress\)** | String | Evet | Üye işyeri tarafındaki fatura adresi şehir bilgisi. |
| **country\(BillingAddress\)** | String | Evet | Üye işyeri tarafındaki fatura adresi ülke bilgisi. |
| **address\(BillingAddress\)** | String | Evet | Üye işyeri tarafındaki fatura adresi. |
| **zipCode\(BillingAddress\)** | String | Hayır | Üye işyeri tarafındaki fatura adresi posta kodu. |
| **contactName\(ShippingAddress\)** | String | Evet | Üye işyeri tarafındaki teslimat adresi, ad, soyad bilgisi. Sepetteki ürünlerden en az 1 tanesi fiziksel ürün \(itemType=PHYSICAL\) ise zorunludur. |
| **city\(ShippingAddress\)** | String | Evet | Üye işyeri tarafındaki teslimat adresi şehir bilgisi. Sepetteki ürünlerden en az 1 tanesi fiziksel ürün \(itemType=PHYSICAL\) ise zorunludur. |
| **country\(ShippingAddress\)** | String | Evet | Üye işyeri tarafındaki teslimat adresi ülke bilgisi. Sepetteki ürünlerden en az 1 tanesi fiziksel ürün \(itemType=PHYSICAL\) ise zorunludur. |
| **address\(ShippingAddress\)** | String | Evet | Üye işyeri tarafındaki teslimat adresi. Sepetteki ürünlerden en az 1 tanesi fiziksel ürün \(itemType=PHYSICAL\) ise zorunludur. |
| **zipCode\(ShippingAddress\)** | String | Hayır | Üye işyeri tarafındaki teslimat adresi posta kodu. |
| **id\(BasketItems\)** | String | Evet | Üye işyeri tarafındaki sepetteki ürüne ait id. |
| **itemType\(BasketItems\)** | String | Evet | Üye işyeri tarafındaki sepetteki ürüne ait tip. Geçerli enum değerler: **PHYSICAL** ve **VIRTUAL**. |
| **name\(BasketItems\)** | String | Evet | Üye işyeri tarafındaki sepetteki ürüne ait isim. |
| **category1\(BasketItems\)** | String | Evet | Üye işyeri tarafındaki sepetteki ürüne ait kategori 1. |
| **category2\(BasketItems\)** | String | Hayır | Üye işyeri tarafındaki sepetteki ürüne ait kategori 2. |
| **price\(BasketItems\)** | Decimal | Evet | Üye işyeri tarafındaki sepetteki ürüne ait tutar. 0 ve 0’dan küçük olamaz, tutarlar toplamı sepet tutarına \(price\) eşit olmalıdır. |
{% endtab %}

{% tab title="Dönüş Parametreleri" %}
| **Parametre İsmi** | **Tip** | **Açıklama** |
| :--- | :--- | :--- |
| **status** | String | Yapılan isteğin sonucunu bildirir. İşlem başarılı ise success, hatalı ise failure döner. |
| **errorCode** | String | İşlem hatalıysa, bu hataya dair belirtilen koddur. |
| **errorMessage** | String | İşlem hatalıysa, bu hataya dair belirtilen mesajdır, locale parametresine göre dil desteği sunar. |
| **errorGroup** | String | İşlem hatalıysa, bu hataya dair belirtilen gruptur. |
| **locale** | String | İstekte belirtilen locale değeri geri dönülür, varsayılan değeri tr’dir. |
| **systemTime** | Long | Dönen sonucun o anki unix timestamp değeridir. |
| **conversationId** | String | İstek esnasında gönderilmişse, sonuçta aynen geri iletilir. |
| **htmlContent** | String | Müşterinin ekranında gösterilmesi gereken 3D şifre ekranını oluşturan HTML sayfası. |
{% endtab %}

{% tab title="Örnek Response" %}
```text
{  
   "status":"success",
   "locale":"tr",
   "systemTime":1528109825882,
   "conversationId":"123456789",
   "threeDSHtmlContent":"PCFkb2N0eXBlIGh0bWw+CjxodG1sIGxhbmc9ImVuIj4KPGhlYWQ+CiAgICA8dGl0bGU+aXl6aWNvIE1vY2sgM0QtU2VjdXJlIFByb2Nlc3NpbmcgUGFnZTwvdGl0bGU+CjwvaGVhZD4KPGJvZHk+Cjxmb3JtIGlkPSJpeXppY28tM2RzLWZvcm0iIGFjdGlvbj0iaHR0cHM6Ly9zYW5kYm94LWFwaS5peXppcGF5LmNvbS9wYXltZW50L21vY2svaW5pdDNkcyIgbWV0aG9kPSJwb3N0Ij4KICAgIDxpbnB1dCB0eXBlPSJoaWRkZW4iIG5hbWU9Im9yZGVySWQiIHZhbHVlPSJtb2NrMTItMjQ3NDIyMTYxMjc1MDQ1NGl5emlvcmQiPgogICAgPGlucHV0IHR5cGU9ImhpZGRlbiIgbmFtZT0iYmluIiB2YWx1ZT0iNTUyODc5Ij4KICAgIDxpbnB1dCB0eXBlPSJoaWRkZW4iIG5hbWU9InN1Y2Nlc3NVcmwiIHZhbHVlPSJodHRwczovL3NhbmRib3gtYXBpLml5emlwYXkuY29tL3BheW1lbnQvaXl6aXBvcy9jYWxsYmFjazNkcy9zdWNjZXNzLzMiPgogICAgPGlucHV0IHR5cGU9ImhpZGRlbiIgbmFtZT0iZmFpbHVyZVVybCIgdmFsdWU9Imh0dHBzOi8vc2FuZGJveC1hcGkuaXl6aXBheS5jb20vcGF5bWVudC9peXppcG9zL2NhbGxiYWNrM2RzL2ZhaWx1cmUvMyI+CiAgICA8aW5wdXQgdHlwZT0iaGlkZGVuIiBuYW1lPSJjb25maXJtYXRpb25VcmwiIHZhbHVlPSJodHRwczovL3NhbmRib3gtYXBpLml5emlwYXkuY29tL3BheW1lbnQvbW9jay9jb25maXJtM2RzIj4KICAgIDxpbnB1dCB0eXBlPSJoaWRkZW4iIG5hbWU9IlBhUmVxIiB2YWx1ZT0iZDUyZDk3MjgtYWQwOS00M2ZhLTk4YjAtMTBkNTUzMmY0ZDhlIj4KPC9mb3JtPgo8c2NyaXB0IHR5cGU9InRleHQvamF2YXNjcmlwdCI+CiAgICBkb2N1bWVudC5nZXRFbGVtZW50QnlJZCgiaXl6aWNvLTNkcy1mb3JtIikuc3VibWl0KCk7Cjwvc2NyaXB0Pgo8L2JvZHk+CjwvaHRtbD4="
}
```
{% endtab %}
{% endtabs %}

{% hint style="success" %}
**threedsHtmlContent** parmetresini ekrana bastırdığınızda kullanıcının tarayıcısı, bankanın 3ds sayfasına yönlenecektir. Kart sahibi cep telefonuna gelen şifreyi girdikten sonra otomatik olarak callbackUrl parametresinde belirttiğiniz adrese yönlenecek ve iyzico bu adrese aşağıdaki değerleri post edecektir.
{% endhint %}

{% hint style="warning" %}
Eğer status failure gelir ise bu, banka bu kart ile 3D işlemine başlanması için uygun olan HTML datasını göndermemiş demektir.
{% endhint %}

### CallbackUrl adresine post edilen değerler

| **Parametre İsmi** | **Veri Tipi** | **Açıklama** |
| :--- | :--- | :--- |
| **status** | String | Yapılan isteğin sonucunu bildirir. İşlem başarılı ise success, hatalı ise failure döner. |
| **paymentId** | String | İşlem success yani başarılı ise, iyzico tarafından o ödemeye verilen değerdir. 3D bitirme sorgusunda kullanılacaktır. |
| **conversationData** | String | İşlem success yani başarılı ise, iyzico tarafından o ödemeye verilen değerdir. Bütün durumlarda dolu gelmeyebilir. Eğer dolu gelirse bu parametrenin de 3D bitirme sorgusunda gönderilmesi gerekir. |
| **conversationId** | Long | Başlatma sorgusunda gönderilen conversationId değeridir. |
| **mdStatus** | String | Bilgilendirme amaçlı dönen mdStatus değeridir. Başarılı durumlar için **1** başarısız durumlar için ise **0,2,3,4,5,6,7,8** olarak dönebilir. |

### 3ds süreci hakkında sık sorulan sorular

#### 1-3ds şifresi gelmiyor

Eğer kart sahibi, tarayıcısında bankasının 3d güvenlik ekranını görümüş ise, bu noktada kart sahibi ile kart bankası başbaşa demektir. Kart bankası tarafından, bankada tanımlı olan telefon numarasına şifre gönderilmektedir. 

Eğer telefona şifre gelmiyor ise; 

* Bankada başka bir telefon kayıtlı olabilir.
* Telefon hatlarındaki bir sorun sebebi ile güvenlik mesajı ulaşmamış olabilir.
* Banka sms gönderim sistemindeki bir aksaklıktan dolayı güvenlik mesajı iletilememiş olabilir. 

Bu durumda, kart sahibi ilk olarak bankası ile iletişime geçerek, 3ds güvenlik şifresinin gönderildiği telefon numarasını kontrol edebilir.

#### 2- 3ds ekranı görünmeden callbackUrl adresine yönleniyor

_**`threedsHtmlContent`**_ içeriği tamamen banka tarafından iletilmektedir. Bu script kullanıcı önce banla domainine yönlendirip, ardından 3ds güvenlik ekranı görmeden, callbackUrl adresinize yönlendiriyor ise, kullanılan kartta gerekli 3ds özellikleri tanımlı değil veya 3ds ile işlem isteği bankası tarafından onaylanmamış demektir. 

### Örnek kodlar

* [Php](https://github.com/iyzico/iyzipay-php/blob/master/samples/initialize_threeds.php#L1)
* [.Net](https://github.com/iyzico/iyzipay-dotnet/blob/master/Iyzipay.Samples/ThreedsSample.cs#L11)
* [Java](https://github.com/iyzico/iyzipay-java/blob/master/src/test/java/com/iyzipay/sample/ThreedsSample.java#L17)
* [Ruby](https://github.com/iyzico/iyzipay-ruby/blob/master/spec/threeds_payment_spec.rb#L13)
* [Python](https://github.com/iyzico/iyzipay-python/blob/master/samples/initialize_threeds.py#L11)
* [Node.js](https://github.com/iyzico/iyzipay-node/blob/master/samples/IyzipaySamples.js#L864)

