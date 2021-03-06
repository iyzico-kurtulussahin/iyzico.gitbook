---
description: >-
  Kullanıcıdan alınan sipariş bilgileri ile sorgu yapılarak, ödeme formu scripti
  çağrılır.
---

# Başlat

{% embed data="{\"url\":\"https://github.com/iyzico/iyzipay-php/blob/master/samples/initialize\_checkout\_form.php\#L1\",\"type\":\"link\",\"title\":\"iyzico/iyzipay-php\",\"description\":\"iyzipay-php - iyzipay api php client\",\"icon\":{\"type\":\"icon\",\"url\":\"https://github.com/fluidicon.png\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://avatars2.githubusercontent.com/u/3815564?s=400&v=4\",\"width\":200,\"height\":200,\"aspectRatio\":1},\"caption\":\"Ödeme formu başlatma sorgusu için Php örneği \"}" %}

{% hint style="info" %}
Dönen cevap içerisindeki **checkoutFormContent** parametresi iyzico ödeme formunu oluşturmak için gerekli HTML kodunu içermektedir. **chekoutFormContent** parametresini bastırdığınız sayfada aşağıdaki "div" satırını eklediğiniz alanda ödeme formu oluşacaktır.
{% endhint %}

#### **Responsive kullanım**

`<div id="iyzipay-checkout-form" class="responsive"></div>`

#### **Pop-up kullanım**

`<div id="iyzipay-checkout-form" class="popup"></div>`

### Paramatreler

{% tabs %}
{% tab title="İstek Parametreleri" %}
| **Parametre ismi** | **Tip** | **Zorunluluk** | **Açıklama** |
| :--- | :--- | :--- | :--- |
| **locale** | string | Hayır | iyzico istek sonucunda dönen metinlerin dilini ayarlamak için kullanılır. Varsayılan değeri tr’dir. |
| **conversationId** | string | Hayır | İstek esnasında gönderip, sonuçta alabileceğiniz bir değer, request/response eşleşmesi yapmak için kullanılabilir. |
| **price** | Decimal | Evet | Ödeme sepet tutarı. Kırılım tutarlar toplamı, sepet tutarına eşit olmalı. |
| **paidPrice** | Decimal | Evet | İndirim, vergi gibi değerlerin dahil edildiği, vade farkı öncesi tutar değeri. |
| **currency** | String | Evet | Para birimi. Default değeri TRY’dir. Kullanılabilen diğer değerler ise USD, EUR, GBP ve IRR’dir. |
| **installment** | Integer | Evet | Taksit bilgisi, tek çekim için 1 gönderilmelidir. Geçerli değerler: 1, 2, 3, 6, 9. |
| **basketId** | String | Hayır | Üye işyeri sepet id’si. |
| **paymentChannel** | String | Hayır | Ödeme kanalı. Geçerli değerler enum içinde sunulmaktadır: WEB, MOBILE, MOBILE\_WEB, MOBILE\_IOS, MOBILE\_ANDROID, MOBILE\_WINDOWS, MOBILE\_TABLET, MOBILE\_PHONE |
| **paymentGroup** | String | Hayır | Ödeme grubu, varsayılan PRODUCT. Geçerli değerler enum içinde sunulmaktadır: PRODUCT, LISTING, SUBSCRIPTION |
| **callbackUrl** | String | Evet | Ödeme akışında üye işyerine başarılı ve hatalı sonucu bildirmek üzere alınan URL adresi. |
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
| **registrationDate\(Buyer\)** | String | Hayır | Üye işyeri tarafındaki alıcıya ait kayıt tarihi. Tarih formatı 2015-09- 17 23:45:06 şeklinde olmalıdır. |
| **lastLoginDate\(Buyer\)** | String | Hayır | Üye işyeri tarafındaki alıcıya ait son giriş tarihi. Tarih formatı 2015- 09-17 23:45:06 şeklinde olmalıdır. |
| **contactName\(BillingAddress\)** | String | Evet | Üye işyeri tarafındaki fatura adresi, ad, soyad bilgisi. |
| **city\(BillingAddress\)** | String | Evet | Üye işyeri tarafındaki fatura adresi şehir bilgisi. |
| **country\(BillingAddress\)** | String | Evet | Üye işyeri tarafındaki fatura adresi ülke bilgisi. |
| **address\(BillingAddress\)** | String | Evet | Üye işyeri tarafındaki fatura adresi. |
| **zipCode\(BillingAddress\)** | String | Hayır | Üye işyeri tarafındaki fatura adresi posta kodu. |
| **contactName\(ShippingAddress\)** | String | Evet | Üye işyeri tarafındaki teslimat adresi ad soyad bilgisi. Sepetteki ürünlerden en az 1 tanesi fiziksel ürün \(itemType=PHYSICAL\) ise zorunludur. |
| **city\(ShippingAddress\)** | String | Evet | Üye işyeri tarafındaki teslimat adresi şehir bilgisi. Sepetteki ürünlerden en az 1 tanesi fiziksel ürün \(itemType=PHYSICAL\) ise zorunludur. |
| **country\(ShippingAddress\)** | String | Evet | Üye işyeri tarafındaki teslimat adresi ülke bilgisi. Sepetteki ürünlerden en az 1 tanesi fiziksel ürün \(itemType=PHYSICAL\) ise zorunludur. |
| **address\(ShippingAddress\)** | String | Evet | Üye işyeri tarafındaki teslimat adresi. Sepetteki ürünlerden en az 1 tanesi fiziksel ürün \(itemType=PHYSICAL\) ise zorunludur. |
| **zipCode\(ShippingAddress\)** | String | Hayır | Üye işyeri tarafındaki teslimat adresi posta kodu. |
| **id\(BasketItem\)** | String | Evet | Üye işyeri tarafındaki sepetteki ürüne ait id. |
| **itemType\(BasketItem\)** | String | Evet | Üye işyeri tarafındaki sepetteki ürüne ait tip. Geçerli enum değerler: PHYSICAL ve VIRTUAL |
| **name\(BasketItem\)** | String | Evet | Üye işyeri tarafındaki sepetteki ürüne ait ismi. |
| **category1\(BasketItem\)** | String | Evet | Üye işyeri tarafındaki sepetteki ürüne ait kategori 1. |
| **category2\(BasketItem\)** | String | Hayır | Üye işyeri tarafındaki sepetteki ürüne ait kategori 2. |
| **price\(BasketItem\)** | Decimal | Evet | Üye işyeri tarafındaki sepetteki ürüne ait tutar. 0 ve 0’dan küçük olamaz, tutarlar toplamı sepet tutarına \(price\) eşit olmalıdır. |
{% endtab %}

{% tab title="Dönüş Parametreleri" %}
| **Parametre ismi** | **Tip** | **Açıklama** |
| :--- | :--- | :--- |
| **checkoutFormContent** | string | Checkout formun açılması için gereken HTML kod. |
| **paymentPageUrl** | string | iyzico ortak ödeme sayfasına erişimi için gereken URL. |
| **token** | string | Checkout form için oluşturulan tekil değer. Her istek için özel üretilir ve işyerine dönülür. Ödemenin sonucunu öğrenmek için zorunlu bir alandır. |
| **tokenExpireTime** | Integer | Checkout form için üretilmiş olan token değerinin geçerlilik süresi. |
| **status** | string | Yapılan isteğin sonucunu bildirir. İşlem başarılı ise success, hatalı ise failure döner. |
| **errorCode** | string | İşlem hatalıysa, bu hataya dair belirtilen koddur. |
| **errorMessage** | string | İşlem hatalıysa, bu hataya dair belirtilen mesajdır, locale parametresine göre dil desteği sunar. |
| **errorGroup** | string | İşlem hatalıysa, bu hataya dair belirtilen gruptur. |
| **locale** | string | İstekte belirtilen locale değeri geri dönülür, varsayılan değeridir. |
| **systemTime** | integer | Dönen sonucun o anki unix timestamp değeridir. |
| **conversationId** | string | İstek esnasında gönderilmişse, sonuçta aynen geri iletilir. |
{% endtab %}

{% tab title="Örnek response" %}
```text
{
    "status": "success",
    "locale": "tr",
    "systemTime": 1470731039071,
    "conversationId": "123456789",
    "token": "d9a1d90e-7cfb-4ead-a6ec-34237bac04f0",
    "checkoutFormContent": "<script type=\"text/javascript\">if (typeof iyziInit == 'undefined') {var iyziInit = {currency:'TRY',token:'d9a1d90e-7cfb-4ead-a6ec-34237bac04f0',price:1.20,locale:'tr',baseUrl:'https://sandbox-api.iyzipay.com',registerCardEnabled:true,bkmEnabled:true,userCards:[],force3Ds:false, isSandbox:true, createTag:function(){var iyziCSSTag = document.createElement('link');iyziCSSTag.setAttribute('rel','stylesheet');iyziCSSTag.setAttribute('type','text/css');iyziCSSTag.setAttribute('href','https://sandbox-static.iyzipay.com/checkoutform/css/main.min.css?v=1470731039031');document.head.appendChild(iyziCSSTag);var iyziJSTag = document.createElement('script');iyziJSTag.setAttribute('src','https://sandbox-static.iyzipay.com/checkoutform/js/iyziCheckout.min.js?v=1470731039031');document.head.appendChild(iyziJSTag);}};iyziInit.createTag();}</script>",
    "tokenExpireTime": 1800,
    "paymentPageUrl": "https://sandbox-cpp.iyzipay.com?token=d9a1d90e-7cfb-4ead-a6ec-34237bac04f0&lang=tr"
}
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
iyzico, ödeme formuna kart bilgileri girilip "X TL Öde" butonuna basıldıktan sonra; ödeme formunu oluştururken belirlenen callbackUrl adresine yönlenir ve bu adrese bir **token** değeri post edilir. 

Bu **token** değeri ile ikinci bir sorgu yapılması gerekmektedir. Yapılacak olan ikinci sorgu ile, işlem sonucuna dair ayrıntılar alınmaktadır. Bu sorgu hakkında ayrıntılı bilgiyi ["ödeme formu sonuç"](https://iyzico.gitbook.io/tr/yazilim-bilgisi-gerekli/odeme-formu/sonuc) sayfamızda bulabilirsiniz.
{% endhint %}

### **Örnek Kodlar**

* [Php](https://github.com/iyzico/iyzipay-php/blob/master/samples/initialize_checkout_form.php#L1)
* [.Net](https://github.com/iyzico/iyzipay-dotnet/blob/master/Iyzipay.Samples/CheckoutFormSample.cs#L11)
* [Java](https://github.com/iyzico/iyzipay-java/blob/master/src/test/java/com/iyzipay/sample/CheckoutFormSample.java#L17)
* [Ruby](https://github.com/iyzico/iyzipay-ruby/blob/master/spec/checkout_form_spec.rb#L13)
* [Python](https://github.com/iyzico/iyzipay-python/blob/master/samples/initialize_checkout_form.py#L11)
* [Node.js](https://github.com/iyzico/iyzipay-node/blob/master/samples/IyzipaySamples.js#L231)

