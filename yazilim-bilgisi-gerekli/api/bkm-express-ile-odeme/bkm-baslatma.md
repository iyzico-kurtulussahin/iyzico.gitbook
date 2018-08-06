# Bkm Başlatma

{% embed data="{\"url\":\"https://github.com/iyzico/iyzipay-php/blob/master/samples/initialize\_bkm.php\#L1\",\"type\":\"link\",\"title\":\"iyzico/iyzipay-php\",\"description\":\"iyzipay-php - iyzipay api php client\",\"icon\":{\"type\":\"icon\",\"url\":\"https://github.com/fluidicon.png\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://avatars2.githubusercontent.com/u/3815564?s=400&v=4\",\"width\":200,\"height\":200,\"aspectRatio\":1},\"caption\":\"Bkm Express başlatma sorgusu Php örneği\"}" %}

### Parametreler

{% tabs %}
{% tab title="İstek parametreleri" %}
| **Parametre İsmi** | **Tip** | **Zorunlu** | **Açıklama** |
| :--- | :--- | :--- | :--- |
| **locale** | String | Hayır | iyzico istek sonucunda dönen metinlerin dilini ayarlamak için kullanılır. Varsayılan değeri tr’dir. **en** kullanılabilir. |
| **conversationId** | String | Hayır | İstek esnasında gönderip, sonuçta alabileceğiniz bir değer, request/response eşleşmesi yapmak için kullanılabilir. En yaygın kullanış biçimi üye işyerinin sipariş numarasıdır. |
| **price** | Decimal | Evet | Ödeme sepet tutarı. Kırılım \(sepetin içerisindeki ürünler\) tutarlar toplamı sepet tutarına eşit olmalı. |
| **currency** | String | Evet | Ödemenin alınacağı para birimi default TRY olarak belirlenmiştir. Diğer değerler ise USD, EUR ve GBP. |
| **installment** | Integer | Evet | Taksit bilgisi, tek çekim için **1** gönderilmelidir. Geçerli değerler: **1**, **2**, **3**, **6**, **9**, **12**. |
| **basketId** | String | Hayır | Üye işyeri tarafından ilgili ödemenin sepetini tanımlamak için kullanılan id'dir. Sipariş numarası veya anlamlı bir değer olabilir. |
| **paymentChannel** | String | Hayır | Ödeme kanalı. Geçerli değerler enum içinde sunulmaktadır: WEB, MOBILE, MOBILE\_WEB, MOBILE\_IOS, MOBILE\_ANDROID, MOBILE\_WINDOWS, MOBILE\_TABLET, MOBILE\_PHONE |
| **paymentGroup** | String | Hayır | Ödeme grubu, varsayılan **PRODUCT**. Geçerli değerler enum içinde sunulmaktadır: **PRODUCT**, **LISTING**, **SUBSCRIPTION**, **OTHER** |
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
| **contactName\(BillingAddress\)** | String | Evet | Üye işyeri tarafındaki fatura adresi, ad, soyad bilgisi. |
| **city\(BillingAddress\)** | String | Evet | Üye işyeri tarafındaki fatura adresi şehir bilgisi. |
| **country\(BillingAddress\)** | String | Evet | Üye işyeri tarafındaki fatura adresi ülke bilgisi. |
| **address\(BillingAddress\)** | String | Evet | Üye işyeri tarafındaki fatura adresi. |
| **zipCode\(BillingAddress\)** | String | Hayır | Üye işyeri tarafındaki fatura adresi posta kodu. |
| **contactName \(ShippingAddress\)** | String | Evet | Üye işyeri tarafındaki teslimat adresi, ad, soyad bilgisi. Sepetteki ürünlerden en az 1 tanesi fiziksel ürün \(itemType=PHYSICAL\) ise zorunludur. |
| **city\(ShippingAddress\)** | String | Evet | Üye işyeri tarafındaki teslimat adresi şehir bilgisi. Sepetteki ürünlerden en az 1 tanesi fiziksel ürün \(itemType=PHYSICAL\) ise zorunludur. |
| **country\(ShippingAddress\)** | String | Evet | Üye işyeri tarafındaki teslimat adresi ülke bilgisi. Sepetteki ürünlerden en az 1 tanesi fiziksel ürün \(itemType=PHYSICAL\) ise zorunludur. |
| **address\(ShippingAddress\)** | String | Evet | Üye işyeri tarafındaki teslimat adresi. Sepetteki ürünlerden en az 1 tanesi fiziksel ürün \(itemType=PHYSICAL\) ise zorunludur. |
| **zipCode\(ShippingAddress\)** | String | Hayır | Üye işyeri tarafındaki teslimat adresi posta kodu. |
| **id\(BasketItems\)** | String | Evet | Üye işyeri tarafındaki sepetteki ürüne ait id. |
| **itemType\(BasketItems\)** | String | Evet | Üye işyeri tarafındaki sepetteki ürüne ait tip. Geçerli enum değerler: PHYSICAL ve VIRTUAL |
| **name\(BasketItems\)** | String | Evet | Üye işyeri tarafındaki sepetteki ürüne ait isim. |
| **category1\(BasketItems\)** | String | Evet | Üye işyeri tarafındaki sepetteki ürüne ait kategori 1. |
| **category2\(BasketItems\)** | String | Hayır | Üye işyeri tarafındaki sepetteki ürüne ait kategori 2. |
| **price\(BasketItems\)** | Decimal | Evet | Üye işyeri tarafındaki sepetteki ürüne ait tutar. 0 ve 0’dan küçük olamaz, tutarlar toplamı sepet tutarına \(price\) eşit olmalıdır. |
{% endtab %}

{% tab title="Dönüş parametreleri" %}
| **Parametre İsmi** | **Tip** | **Açıklama** |
| :--- | :--- | :--- |
| **status** | String | Yapılan isteğin sonucunu bildirir. İşlem başarılı ise success, hatalı ise failure döner. |
| **errorCode** | String | İşlem hatalıysa, bu hataya dair belirtilen koddur. |
| **errorMessage** | String | İşlem hatalıysa, bu hataya dair belirtilen mesajdır. Locale parametresine göre dil desteği sunar. |
| **errorGroup** | String | İşlem hatalıysa, bu hataya dair belirtilen gruptur. |
| **locale** | String | İstekte belirtilen locale değeri geri dönülür, varsayılan değeri tr’dir. |
| **systemTime** | Long | Dönen sonucun o anki unix timestamp değeridir. |
| **conversationId** | String | İstek esnasında gönderilmişse, sonuçta aynen geri iletilir. |
| **htmlContent** | String | Render edildiğinde gerekli yönlendirmenin yapılmasını sağlayan içerik. |
| **redirectUrl** | String | Yönlendirme yapabileceğiniz bağlantı adresi. |
| **token** | String | Ödeme isteğine özel, iyzico tarafından oluşturulan değer. |
| **tokenExpireTime** | String | Tokenin geçerlilik süresi. |
{% endtab %}

{% tab title="Örnek response" %}
```text
{
   "status":"success",
   "locale":"tr",
   "systemTime":1527841231478,
   "conversationId":"123456789",
   "htmlContent":"PCFkb2N0eXBlIGh0bWw+CjxodG1sPgo8aGVhZD4KICAgIDxtZXRhIGNoYXJzZXQ9IlVURi04Ii8+CiAgICA8dGl0bGU+QktNIEluaXRpYWxpemVyPC90aXRsZT4KPC9oZWFkPgo8Ym9keT4KPGRpdj4KICAgIDxmb3JtIGlkPSJia21IaWRkZW5Gb3JtIiBtZXRob2Q9InBvc3QiIGFjdGlvbj0iaHR0cHM6Ly9zYW5kYm94LWFwaS5peXppcGF5LmNvbS9wYXltZW50L2JrbS9tb2NrL2luaXRpYWxpemUiID4KICAgICAgICA8aW5wdXQgdHlwZT0iaGlkZGVuIiBuYW1lPSJ0IiB2YWx1ZT0ibW9ja1Rva2VuXzE1Mjc4NDEyMzE0NjYiLz4KICAgICAgICA8aW5wdXQgdHlwZT0iaGlkZGVuIiBuYW1lPSJ0cyIgdmFsdWU9IjE1Mjc4NDEyMzE0NjYiLz4KICAgICAgICA8aW5wdXQgdHlwZT0iaGlkZGVuIiBuYW1lPSJzIiB2YWx1ZT0iMzViMjRiZjMtZmRmZi00ODY1LWE1NWUtMDFlNTdjY2M5NDI5Ii8+CiAgICAgICAgPHNjcmlwdD5kb2N1bWVudC5nZXRFbGVtZW50QnlJZCgnYmttSGlkZGVuRm9ybScpLnN1Ym1pdCgpOzwvc2NyaXB0PgogICAgPC9mb3JtPgo8L2Rpdj4KPC9ib2R5Pgo8L2h0bWw+",
   "token":"mockToken_1527841231466"
}
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
**htmlContent** parametresini ekrana bastırdığınızda BKM Express login ekranı görüntülenecektir. Hesap sahibi login olduğunda ve kartını seçip ödeme yaptıktan sonra otomatik olarak callbackUrl parametresinde belirttiğiniz adrese yönlenecek ve iyzico bu adrese aşağıdaki değerleri post edecektir.

BKM Express işlem sonucunu öğrenebilmek için dönüş adresinize\(callbackUrl\) aşağıdaki parametre dönecektir.
{% endhint %}

| **Parametre İsmi** | **Tip** | **Açıklama** |
| :--- | :--- | :--- |
| **token** | String | Başlatma esnasında sizin ile paylaşılan BKM ödeme sonucunu taşıyan değerdir |

### Örnek kodlar

* [Php](https://github.com/iyzico/iyzipay-php/blob/master/samples/initialize_bkm.php#L1)
* [.Net](https://github.com/iyzico/iyzipay-dotnet/blob/develop/Iyzipay.Samples/BkmSample.cs#L97)
* [Java](https://github.com/iyzico/iyzipay-java/blob/master/src/test/java/com/iyzipay/sample/BkmSample.java#L17)
* [Ruby](https://github.com/iyzico/iyzipay-ruby/blob/master/spec/bkm_spec.rb#L13)
* [Python](https://github.com/iyzico/iyzipay-python/blob/master/samples/initialize_bkm.py#L11)
* [Node.js](https://github.com/iyzico/iyzipay-node/blob/master/samples/IyzipaySamples.js#L68)



