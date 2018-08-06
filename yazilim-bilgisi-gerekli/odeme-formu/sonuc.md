# Sonuç

{% embed data="{\"url\":\"https://github.com/iyzico/iyzipay-php/blob/master/samples/retrieve\_checkout\_form\_result.php\#L1\",\"type\":\"link\",\"title\":\"iyzico/iyzipay-php\",\"description\":\"iyzipay-php - iyzipay api php client\",\"icon\":{\"type\":\"icon\",\"url\":\"https://github.com/fluidicon.png\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://avatars2.githubusercontent.com/u/3815564?s=400&v=4\",\"width\":200,\"height\":200,\"aspectRatio\":1},\"caption\":\"Ödeme formu sonucu sorgusu için Php örneği\"}" %}

### Parametreler

{% tabs %}
{% tab title="İstek Parametreleri" %}
| **Parametre ismi** | **Tip** | **Zorunluluk** | **Açıklama** |
| :--- | :--- | :--- | :--- |
| **locale** | string | Hayır | iyzico istek sonucunda dönen metinlerin dilini ayarlamak için kullanılır. Varsayılan değeri tr’dir. |
| **conversationId** | string | Hayır | İstek esnasında gönderip, sonuçta alabileceğiniz bir değer, request/response eşleşmesi yapmak için kullanılabilir. |
| **token** | string | Evet | Checkout form için oluşturulan tekil değer. Her istek için özel üretilir ve işyerine dönülür. Ödemenin sonucunu öğrenmek için zorunlu bir alandır. |
{% endtab %}

{% tab title="Dönüş Parametreleri" %}
| **Parametre İsmi** | **Veri Tipi** | **Açıklama** |
| :--- | :--- | :--- |
| **token** | String | Checkout form için oluşturulan tekil değer. Her istek için özel üretilir ve işyerine dönülür. Ödemenin sonucunu öğrenmek için zorunlu bir alandır. |
| **callbackUrl** | String | Ödeme akışında üye işyerine başarılı ve hatalı sonucu bildirmek üzere alınan URL adresi. |
| **status** | String | Yapılan isteğin sonucunu bildirir. Başarılı ise success, hatalı ise failure döner. |
| **paymentStatus** | String | Ödeme isteğinin durumunu gösterir. Success ise karttan ilgili tutar çekilmiştir. SUCCESS, FAILURE, INIT\_THREEDS, CALLBACK\_THREEDS, BKM\_POS\_SELECTED, CALLBACK\_PECCO |
| **errorCode** | String | İşlem hatalıysa, bu hataya dair belirtilen koddur. |
| **errorMessage** | String | İşlem hatalıysa, bu hataya dair belirtilen mesajdır, locale parametresine göre dil desteği sunar. |
| **errorGroup** | String | İşlem hatalıysa, bu hataya dair belirtilen gruptur. |
| **locale** | String | İstekte belirtilen locale değeri geri dönülür, varsayılan değeri tr’dir. |
| **systemTime** | Long | Dönen sonucun o anki unix timestamp değeridir. |
| **conversationId** | String | İstek esnasında gönderilmişse, sonuçta aynen geri iletilir. |
| **paymentId** | String | Ödemeye ait id, üye işyeri tarafından mutlaka saklanmalıdır. Ödemenin iptali ve iyzico ile iletişimde kullanılır. |
| **price** | Decimal | Ödeme sepet tutarı. Kırılım tutarlar toplamı sepet tutarına eşit olmalı. |
| **paidPrice** | Decimal | İndirim vade farkı vs. hesaplanmış POS’tan geçen, tahsil edilen, nihai tutar. |
| **currency** | String | Ödemenin alındığı para birimi. |
| **installment** | Integer | Ödemenin taksit bilgisi, tek çekim için 1 döner. Geçerli değerler: 1, 2, 3, 6, 9, 12 |
| **paymentStatus** | String | İşlemin sonucunu gösterir. Geçerli değerler SUCCESS, FAILURE, INIT\_THREEDS, CALLBACK\_THREEDS, BKM\_POS\_SELECTED, CALLBACK\_PECCO |
| **basketId** | String | Üye işyeri tarafından gönderilen sepet id’si. |
| **binNumber** | String | Ödeme yapılan kartın ilk 6 hanesi. |
| **lastFourDigits** | String | Ödeme yapılan kartın son 4 hanesi. |
| **cardAssociation** | String | Eğer ödeme yapılan kart yerel bir kart ise, kartın ait olduğu kuruluş. Geçerli değerler: VISA, MASTER\_CARD, AMERICAN\_EXPRESS, TROY |
| **cardFamily** | String | Eğer ödeme yapılan kart yerel bir kart ise, kartın ait olduğu aile. Geçerli değerler: Bonus, Axess, World, Maximum, Paraf, CardFinans, Advantage |
| **cardType** | String | Eğer ödeme yapılan kart yerel bir kart ise, kartın ait olduğu tipi. Geçerli değerler: CREDIT\_CARD, DEBIT\_CARD, PREPAID\_CARD |
| **fraudStatus** | Integer | Ödeme işleminin fraud filtrelerine göre durumu. Eğer ödemenin fraud risk skoru düşük ise ödemeye anında onay verilir bu durumda 1 değeri döner. Eğer fraud risk skoru yüksek ise ödeme işlemi reddedilir ve -1 döner. Eğer ödeme işlemi daha sonradan incelenip karar verilecekse 0 döner. Geçerli değerler: 0, -1 ve 1. Üye işyeri sadece 1 olan işlemlerde ürünü kargoya vermelidir, 0 olan işlemler için bilgilendirme beklemelidir. |
| **iyziCommissionFee** | Decimal | Ödemeye ait iyzico işlem ücreti . |
| **iyziCommissionRateAmount** | Decimal | Ödemeye ait iyzico işlem komisyon tutarı. |
| **merchantCommissionRate** | Decimal | Üye işyerinin uyguladığı vade/komisyon oranı. Örneğin price=100, paidPrice=110 ise üye işyeri vade/komisyon oranı %10’dur. Bilgi amaçlıdır. |
| **merchantCommissionRateAmount** | Decimal | Üye işyerinin uyguladığı vade/komisyon tutarı. Örneğin price=100, paidPrice=110 ise üye işyeri vade/komisyon tutarı 10’dur. Bilgi amaçlıdır. |
| **paymentTransactionId \(ItemTransactions\)** | String | Ödeme kırılımına ait id, üye işyeri tarafından mutlaka saklanmalıdır. Ödeme kırılımının iadesi, onayı, onay geri çekmesi ve iyzico ile iletişimde kullanılır. Tercihen itemId ile ilişkili bir şekilde tutulmalıdır. |
| **itemId \(ItemTransactions\)** | String | Üye işyeri tarafından iletilen, sepetteki ürüne ait id. |
| **price \(ItemTransactions\)** | Decimal | Üye işyeri tarafındaki sepetteki ürüne ait tutar. |
| **paidPrice \(ItemTransactions\)** | Decimal | Tahsilat tutarının kırılım bazındaki dağılımı. Üye işyeri tarafından mutlaka saklanmalıdır. |
| **transactionStatus \(ItemTransactions\)** | Integer | Ödeme kırılımının durumu. Ödeme fraud kontrolünde ise 0 değeri döner, bu durumda fraudStatus değeri de 0’dır. Ödeme, fraud kontrolünden sonra reddedilirse -1 döner. Pazaryeri modelinde ürüne onay verilene dek bu değer 1 olarak döner. Pazaryeri modelinde ürüne onay verilmişse bu değer 2 olur. Geçerli değerler: 0, -1, 1, 2. |
| **blockageRate \(ItemTransactions\)** | Decimal | Kırılım bazında üye işyeri blokaj oranı. iyzico – üye işyeri anlaşmasına göre, üye işyerine işlem bazında blokaj uygulayabilir. Bu blokaj üye işyeri fraud riskini önlemek içindir, blokaj süresi boyunca para iyzico’da tutulur, bu süre sonrasında üye işyerine gönderilir. |
| **blockageRateAmountMerchant \(ItemTransactions\)** | Decimal | Kırılım bazında üye işyeri blokaj tutarının, üye işyerine yansıyan rakamı. Blokaj tutarı mümkün olduğunca üye işyerine yansıtılır. Eğer blokaj tutarı, üye işyeri tutarından daha büyükse bu durumda alt üye işyerine de yansıtılır. |
| **blockageResolvedDate \(ItemTransactions\)** | String | İşlem bazında blokaj çözülme tarihi. yyyy-MM-dd HH:mm:ss formatındadır, örneğin 2015-10-19 14:36:52. |
| **iyziCommissionFee \(ItemTransactions\)** | Decimal | iyzico işlem ücretinin kırılım bazında dağılmış tutarı. |
| **iyziCommissionRateAmount \(ItemTransactions\)** | Decimal | iyzico işlem komisyon tutarının kırılım bazında dağılmış tutarı. |
| **merchantCommissionRate \(ItemTransactions\)** | Decimal | Üye işyerinin uyguladığı vade/komisyon oranının kırılım bazında dağılmış oranı. |
| **merchantCommissionRateAmount \(ItemTransactions\)** | Decimal | Üye işyerinin uyguladığı vade/komisyon tutarıın, kırılım bazında dağılmış tutarı. |
| **merchantPayoutAmount \(ItemTransactions\)** | Decimal | Bu kırılım için, iyzico işlem ücreti, komisyon tutarı ve blokajlar düşüldükten sonra üye işyerine gönderilecek tutar. |
| **paidPrice\(ItemTransactions\) \(convertedPayout\)** | Decimal | Tahsilat tutarının kırılım bazındaki dağılımı. Üye işyeri tarafından mutlaka saklanmalıdır. |
| **iyziCommissionFee \(ItemTransactions\) \(convertedPayout\)** | Decimal | iyzico işlem ücretinin kırılım bazında dağılmış tutarı. |
| **iyziCommissionRateAmount \(ItemTransactions\) \(convertedPayout\)** | Decimal | iyzico işlem komisyon tutarının kırılım bazında dağılmış tutarı. |
| **blockageRateAmountMerchant \(ItemTransactions\) \(convertedPayout\)** | Decimal | Kırılım bazında üye işyeri blokaj tutarının, üye işyerine yansıyan rakamı. Blokaj tutarı mümkün olduğunca üye işyerine yansıtılır. Eğer blokaj tutarı, üye işyeri tutarından daha büyükse bu durumda alt üye işyerine de yansıtılır. |
| **merchantPayoutAmount \(ItemTransactions\) \(convertedPayout\)** | Decimal | Bu kırılım için, iyzico işlem ücreti, komisyon tutarı ve blokajlar düşüldükten sonra üye işyerine gönderilecek tutar. |
| **iyziConversationRate \(ItemTransactions\) \(convertedPayout\)** | Decimal | Bu kırılım için, iyzico işlem ücreti, komisyon tutarı ve blokajlar düşüldükten sonra üye işyerine gönderilecek tutar. |
| **iyziConversationRateAmount \(ItemTransactions\) \(convertedPayout\)** | Decimal | Bu kırılım için, iyzico işlem ücreti, komisyon tutarı ve blokajlar düşüldükten sonra üye işyerine gönderilecek tutar. |
| **currency \(ItemTransactions\) \(convertedPayout\)** | String | Ödemenin alındığı para birimi. |
{% endtab %}

{% tab title="Örnek Response" %}
```text
{  
   "status":"success",
   "locale":"tr",
   "systemTime":1527255323265,
   "conversationId":"123456789",
   "price":0.30000000,
   "paidPrice":1.20000000,
   "installment":1,
   "paymentId":"10805931",
   "fraudStatus":1,
   "merchantCommissionRate":300.00000000,
   "merchantCommissionRateAmount":0.90000000,
   "iyziCommissionRateAmount":0.03150000,
   "iyziCommissionFee":0.25000000,
   "cardType":"CREDIT_CARD",
   "cardAssociation":"MASTER_CARD",
   "cardFamily":"Axess",
   "cardToken":"YW3oTdzBwrzaG3Dh2qR0UzGHjAg=",
   "cardUserKey":"9vd6VuZgY9nstekbL58Otj1T8Zw=",
   "binNumber":"552608",
   "lastFourDigits":"0006",
   "basketId":"B67832",
   "currency":"TRY",
   "itemTransactions":[  
      {  
         "itemId":"BI101",
         "paymentTransactionId":"11391611",
         "transactionStatus":1,
         "price":0.30000000,
         "paidPrice":1.20000000,
         "merchantCommissionRate":300.00000000,
         "merchantCommissionRateAmount":0.90000000,
         "iyziCommissionRateAmount":0.03150000,
         "iyziCommissionFee":0.25000000,
         "blockageRate":10.00000000,
         "blockageRateAmountMerchant":0.12000000,
         "blockageRateAmountSubMerchant":0E-8,
         "blockageResolvedDate":"2018-06-01 16:06:56",
         "subMerchantKey":"pauQrTuLC6mfQBaQFy86NnVGZc0=",
         "subMerchantPrice":0.30000000,
         "subMerchantPayoutRate":100.00000000,
         "subMerchantPayoutAmount":0.30000000,
         "merchantPayoutAmount":0.49850000,
         "convertedPayout":{  
            "paidPrice":1.20000000,
            "iyziCommissionRateAmount":0.03150000,
            "iyziCommissionFee":0.25000000,
            "blockageRateAmountMerchant":0.12000000,
            "blockageRateAmountSubMerchant":0E-8,
            "subMerchantPayoutAmount":0.30000000,
            "merchantPayoutAmount":0.49850000,
            "iyziConversionRate":0E-8,
            "iyziConversionRateAmount":0E-8,
            "currency":"TRY"
         }
      }
   ],
   "authCode":"993325",
   "phase":"AUTH",
   "hostReference":"mock00007iyzihostrfn",
   "token":"f8aee98c-7dad-430e-a20f-70f327f8e64e",
   "callbackUrl":"https://www.merchant.com/callback",
   "paymentStatus":"SUCCESS"
}
```
{% endtab %}
{% endtabs %}

{% api-method method="post" host="" path="" %}
{% api-method-summary %}
Ödeme formu sonuç
{% endapi-method-summary %}

{% api-method-description %}
Ödeme formu ile yapılan işlemin sonucunu almak
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="locale" type="string" required=false %}
iyzico istek sonucunda dönen metinlerin dilini ayarlamak için kullanılır. Varsayılan değeri tr’dir.
{% endapi-method-parameter %}

{% api-method-parameter name="conversationId" type="string" required=false %}
İstek esnasında gönderip, sonuçta alabileceğiniz bir değer, request/response eşleşmesi yapmak için kullanılabilir.
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
Checkout form için oluşturulan tekil değer. Her istek için özel üretilir ve işyerine dönülür. Ödemenin sonucunu öğrenmek için zorunlu bir alandır.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

{% code-tabs %}
{% code-tabs-item title="success" %}
```
{  
   "status":"success",
   "locale":"tr",
   "systemTime":1527255323265,
   "conversationId":"123456789",
   "price":0.30000000,
   "paidPrice":1.20000000,
   "installment":1,
   "paymentId":"10805931",
   "fraudStatus":1,
   "merchantCommissionRate":300.00000000,
   "merchantCommissionRateAmount":0.90000000,
   "iyziCommissionRateAmount":0.03150000,
   "iyziCommissionFee":0.25000000,
   "cardType":"CREDIT_CARD",
   "cardAssociation":"MASTER_CARD",
   "cardFamily":"Axess",
   "cardToken":"YW3oTdzBwrzaG3Dh2qR0UzGHjAg=",
   "cardUserKey":"9vd6VuZgY9nstekbL58Otj1T8Zw=",
   "binNumber":"552608",
   "lastFourDigits":"0006",
   "basketId":"B67832",
   "currency":"TRY",
   "itemTransactions":[  
      {  
         "itemId":"BI101",
         "paymentTransactionId":"11391611",
         "transactionStatus":1,
         "price":0.30000000,
         "paidPrice":1.20000000,
         "merchantCommissionRate":300.00000000,
         "merchantCommissionRateAmount":0.90000000,
         "iyziCommissionRateAmount":0.03150000,
         "iyziCommissionFee":0.25000000,
         "blockageRate":10.00000000,
         "blockageRateAmountMerchant":0.12000000,
         "blockageRateAmountSubMerchant":0E-8,
         "blockageResolvedDate":"2018-06-01 16:06:56",
         "subMerchantKey":"pauQrTuLC6mfQBaQFy86NnVGZc0=",
         "subMerchantPrice":0.30000000,
         "subMerchantPayoutRate":100.00000000,
         "subMerchantPayoutAmount":0.30000000,
         "merchantPayoutAmount":0.49850000,
         "convertedPayout":{  
            "paidPrice":1.20000000,
            "iyziCommissionRateAmount":0.03150000,
            "iyziCommissionFee":0.25000000,
            "blockageRateAmountMerchant":0.12000000,
            "blockageRateAmountSubMerchant":0E-8,
            "subMerchantPayoutAmount":0.30000000,
            "merchantPayoutAmount":0.49850000,
            "iyziConversionRate":0E-8,
            "iyziConversionRateAmount":0E-8,
            "currency":"TRY"
         }
      }
   ],
   "authCode":"993325",
   "phase":"AUTH",
   "hostReference":"mock00007iyzihostrfn",
   "token":"f8aee98c-7dad-430e-a20f-70f327f8e64e",
   "callbackUrl":"https://www.merchant.com/callback",
   "paymentStatus":"SUCCESS"
}

```
{% endcode-tabs-item %}

{% code-tabs-item title="errorCode:5124" %}
```
{
    "status": "failure",
    "errorCode": "5124",
    "errorMessage": "token bulunamadı",
    "locale": "tr",
    "systemTime": 1533548614141,
    "conversationId": "123456789"
}

```
{% endcode-tabs-item %}

{% code-tabs-item title="errorCode:5132" %}
```
{
    "status": "failure",
    "errorCode": "5132",
    "errorMessage": "token gönderilmesi zorunludur",
    "locale": "tr",
    "systemTime": 1533548647114,
    "conversationId": "123456789"
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

iyzico, ödeme formuna kart bilgileri girilip "X TL Öde" butonuna basıldıktan sonra; ödeme formunu oluştururken belirlenen callbackUrl adresine yönlenir ve bu adrese bir **token** değeri post edilir. Bu **token** değeri ile ikinci bir sorgu yapılması gerekmektedir. Yapılacak olan ikinci sorgu ile, işlem sonucuna dair ayrıntılar alınmaktadır. Bu sorguda kullanacağınız **token** değerini ödeme formunu oluşturduğunuz anda ya da callbackUrl adresinize iyzico tarafından post edildiğinde alabilirsiniz.

### **Örnek Kodlar**

* [Php](https://github.com/iyzico/iyzipay-php/blob/master/samples/retrieve_checkout_form_result.php#L1)
* [.Net](https://github.com/iyzico/iyzipay-dotnet/blob/master/Iyzipay.Samples/CheckoutFormSample.cs#L107)
* [Java](https://github.com/iyzico/iyzipay-java/blob/master/src/test/java/com/iyzipay/sample/CheckoutFormSample.java#L112)
* [Ruby](https://github.com/iyzico/iyzipay-ruby/blob/master/spec/checkout_form_spec.rb#L92)
* [Python](https://github.com/iyzico/iyzipay-python/blob/master/samples/retrieve_checkout_form_result.py#L11)
* [Node.js](https://github.com/iyzico/iyzipay-node/blob/master/samples/IyzipaySamples.js#L305)

