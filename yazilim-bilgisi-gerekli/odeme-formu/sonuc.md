---
description: Yapılan ödemenin sonucunu öğrenme sorgusu
---

# Sonuç

{% embed data="{\"url\":\"https://github.com/iyzico/iyzipay-php/blob/master/samples/retrieve\_checkout\_form\_result.php\#L1\",\"type\":\"link\",\"title\":\"iyzico/iyzipay-php\",\"description\":\"iyzipay-php - iyzipay api php client\",\"icon\":{\"type\":\"icon\",\"url\":\"https://github.com/fluidicon.png\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://avatars2.githubusercontent.com/u/3815564?s=400&v=4\",\"width\":200,\"height\":200,\"aspectRatio\":1},\"caption\":\"Ödeme formu sonucu sorgusu için Php örneği\"}" %}

iyzico, ödeme formuna kart bilgileri girilip "X TL Öde" butonuna basıldıktan sonra; ödeme formunu oluştururken belirlenen callbackUrl adresine yönlenir ve bu adrese bir **token** değeri post edilir. 

Bu **token** değeri ile ikinci bir sorgu yapılması gerekmektedir. Yapılacak olan ikinci sorgu ile, işlem sonucuna dair ayrıntılar alınmaktadır. 

Bu sorguda kullanacağınız **token** değerini ödeme formunu oluşturduğunuz anda ya da callbackUrl adresinize iyzico tarafından post edildiğinde alabilirsiniz.

### Parametreler

| **Parametre ismi** | **Açıklama** |
| :--- | :--- |
| **locale** | iyzico istek sonucunda dönen metinlerin dilini ayarlamak için kullanılır. Varsayılan değeri tr’dir. |
| **conversationId** | İstek esnasında gönderip, sonuçta alabileceğiniz bir değer, request/response eşleşmesi yapmak için kullanılabilir. |
| **token** | Checkout form için oluşturulan tekil değer. Her istek için özel üretilir ve işyerine dönülür. Ödemenin sonucunu öğrenmek için zorunlu bir alandır. |

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
istek esnasında gönderip, sonuçta alabileceğiniz bir değer, request/response eşleşmesi yapmak için kullanılabilir. 
{% endapi-method-parameter %}
{% api-method-parameter name="token" type="string" required=false %}
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

### **Örnek Kodlar**

* [Php](https://github.com/iyzico/iyzipay-php/blob/master/samples/retrieve_checkout_form_result.php#L1)
* [.Net](https://github.com/iyzico/iyzipay-dotnet/blob/master/Iyzipay.Samples/CheckoutFormSample.cs#L107)
* [Java](https://github.com/iyzico/iyzipay-java/blob/master/src/test/java/com/iyzipay/sample/CheckoutFormSample.java#L112)
* [Ruby](https://github.com/iyzico/iyzipay-ruby/blob/master/spec/checkout_form_spec.rb#L92)
* [Python](https://github.com/iyzico/iyzipay-python/blob/master/samples/retrieve_checkout_form_result.py#L11)
* [Node.js](https://github.com/iyzico/iyzipay-node/blob/master/samples/IyzipaySamples.js#L305)

