---
description: >-
  Taksit sorgulama(installment), ilgili kart bir kredi kartı ise ve bir taksit
  programına dahil ise, kaç taksit yapılabileceği ve taksit komisyon oranı
  konusunda bilgi vermektedir
---

# Taksit ve Bin Sorgulama

{% embed data="{\"url\":\"https://github.com/iyzico/iyzipay-php/blob/master/samples/retrieve\_installments.php\#L1\",\"type\":\"link\",\"title\":\"iyzico/iyzipay-php\",\"description\":\"iyzipay-php - iyzipay api php client\",\"icon\":{\"type\":\"icon\",\"url\":\"https://github.com/fluidicon.png\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://avatars2.githubusercontent.com/u/3815564?s=400&v=4\",\"width\":200,\"height\":200,\"aspectRatio\":1},\"caption\":\"Taksit sorgulama sorgusu PHP örneği\"}" %}

{% api-method method="post" host="https://api.iyzipay.com/payment/iyzipos/installment" path="" %}
{% api-method-summary %}
Taksit ve Bin Sorgulama
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="price" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="binNumber" type="string" required=false %}
Kartın ilk 6 hanesi
{% endapi-method-parameter %}

{% api-method-parameter name="locale" type="string" required=false %}
Dil
{% endapi-method-parameter %}

{% api-method-parameter name="canversationId" type="string" required=false %}
conversationID
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

{% code-tabs %}
{% code-tabs-item title="Başarılı" %}
```bash
{
    "status": "success",
    "locale": "tr",
    "systemTime": 1470727458044,
    "conversationId": "123456789",
    "installmentDetails": [
        {
            "binNumber": "454360",
            "price": 100,
            "cardType": "CREDIT_CARD",
            "cardAssociation": "VISA",
            "cardFamilyName": "Maximum",
            "force3ds": 0,
            "bankCode": 64,
            "bankName": "İş Bankası",
            "forceCvc": 0,
            "installmentPrices": [
                {
                    "installmentPrice": 100,
                    "totalPrice": 100,
                    "installmentNumber": 1
                },
                {
                    "installmentPrice": 50.68,
                    "totalPrice": 101.36,
                    "installmentNumber": 2
                },
                {
                    "installmentPrice": 33.95,
                    "totalPrice": 101.86,
                    "installmentNumber": 3
                },
                {
                    "installmentPrice": 17.43,
                    "totalPrice": 104.58,
                    "installmentNumber": 6
                },
                {
                    "installmentPrice": 12.19,
                    "totalPrice": 109.67,
                    "installmentNumber": 9
                }
            ]
        }
    ]
}
```
{% endcode-tabs-item %}

{% code-tabs-item title="Hata" %}
```bash
{
    "status": "failure",
    "errorCode": "5007",
    "errorMessage": "binNumber 6 karakter olmalıdır",
    "locale": "tr",
    "systemTime": 1530954203653,
    "conversationId": "123456789"
}
```
{% endcode-tabs-item %}

{% code-tabs-item title="Yabancı bin" %}
```bash
{
    "status": "success",
    "locale": "tr",
    "systemTime": 1530954239376,
    "conversationId": "123456789",
    "installmentDetails": [
        {
            "binNumber": "460341",
            "price": 100,
            "force3ds": 0,
            "forceCvc": 0,
            "installmentPrices": [
                {
                    "installmentPrice": 100,
                    "totalPrice": 100,
                    "installmentNumber": 1
                }
            ]
        }
    ]
}
```
{% endcode-tabs-item %}

{% code-tabs-item title="Tüm taksitler" %}
```bash
{
    "status": "success",
    "locale": "tr",
    "systemTime": 1530954278863,
    "conversationId": "123456789",
    "installmentDetails": [
        {
            "price": 100,
            "cardFamilyName": "Maximum",
            "force3ds": 1,
            "bankCode": 64,
            "bankName": "İş Bankası",
            "forceCvc": 1,
            "installmentPrices": [
                {
                    "installmentPrice": 100,
                    "totalPrice": 100,
                    "installmentNumber": 1
                }
            ]
        },
        {
            "price": 100,
            "cardFamilyName": "World",
            "force3ds": 0,
            "bankCode": 15,
            "bankName": "Vakıfbank",
            "forceCvc": 0,
            "installmentPrices": [
                {
                    "installmentPrice": 100,
                    "totalPrice": 100,
                    "installmentNumber": 1
                },
                {
                    "installmentPrice": 51,
                    "totalPrice": 102,
                    "installmentNumber": 2
                },
                {
                    "installmentPrice": 34.33,
                    "totalPrice": 103,
                    "installmentNumber": 3
                },
                {
                    "installmentPrice": 17.67,
                    "totalPrice": 106,
                    "installmentNumber": 6
                },
                {
                    "installmentPrice": 26,
                    "totalPrice": 104,
                    "installmentNumber": 4
                },
                {
                    "installmentPrice": 21,
                    "totalPrice": 105,
                    "installmentNumber": 5
                }
            ]
        },
        {
            "price": 100,
            "cardFamilyName": "Cardfinans",
            "force3ds": 0,
            "bankCode": 111,
            "bankName": "Finansbank",
            "forceCvc": 0,
            "installmentPrices": [
                {
                    "installmentPrice": 100,
                    "totalPrice": 100,
                    "installmentNumber": 1
                },
                {
                    "installmentPrice": 51,
                    "totalPrice": 102,
                    "installmentNumber": 2
                },
                {
                    "installmentPrice": 30,
                    "totalPrice": 120,
                    "installmentNumber": 4
                }
            ]
        },
        {
            "price": 100,
            "cardFamilyName": "Paraf",
            "force3ds": 0,
            "bankCode": 12,
            "bankName": "Halk Bankası",
            "forceCvc": 0,
            "installmentPrices": [
                {
                    "installmentPrice": 100,
                    "totalPrice": 100,
                    "installmentNumber": 1
                },
                {
                    "installmentPrice": 50.6,
                    "totalPrice": 101.2,
                    "installmentNumber": 2
                },
                {
                    "installmentPrice": 34.11,
                    "totalPrice": 102.33,
                    "installmentNumber": 3
                },
                {
                    "installmentPrice": 17.43,
                    "totalPrice": 104.57,
                    "installmentNumber": 6
                },
                {
                    "installmentPrice": 11.77,
                    "totalPrice": 105.95,
                    "installmentNumber": 9
                }
            ]
        },
        {
            "price": 100,
            "cardFamilyName": "Axess",
            "force3ds": 0,
            "bankCode": 46,
            "bankName": "Akbank",
            "forceCvc": 0,
            "installmentPrices": [
                {
                    "installmentPrice": 100,
                    "totalPrice": 100,
                    "installmentNumber": 1
                },
                {
                    "installmentPrice": 52.14,
                    "totalPrice": 104.28,
                    "installmentNumber": 2
                },
                {
                    "installmentPrice": 34.99,
                    "totalPrice": 104.96,
                    "installmentNumber": 3
                },
                {
                    "installmentPrice": 17.89,
                    "totalPrice": 107.33,
                    "installmentNumber": 6
                },
                {
                    "installmentPrice": 12.2,
                    "totalPrice": 109.81,
                    "installmentNumber": 9
                }
            ]
        },
        {
            "price": 100,
            "cardFamilyName": "Bonus",
            "force3ds": 0,
            "bankCode": 32,
            "bankName": "TEB",
            "forceCvc": 0,
            "installmentPrices": [
                {
                    "installmentPrice": 100,
                    "totalPrice": 100,
                    "installmentNumber": 1
                },
                {
                    "installmentPrice": 50,
                    "totalPrice": 100,
                    "installmentNumber": 2
                },
                {
                    "installmentPrice": 33.34,
                    "totalPrice": 100.03,
                    "installmentNumber": 3
                },
                {
                    "installmentPrice": 16.67,
                    "totalPrice": 100,
                    "installmentNumber": 6
                },
                {
                    "installmentPrice": 11.11,
                    "totalPrice": 100,
                    "installmentNumber": 9
                }
            ]
        },
        {
            "price": 100,
            "cardFamilyName": "Bonus",
            "force3ds": 0,
            "bankCode": 134,
            "bankName": "Denizbank",
            "forceCvc": 0,
            "installmentPrices": [
                {
                    "installmentPrice": 100,
                    "totalPrice": 100,
                    "installmentNumber": 1
                },
                {
                    "installmentPrice": 50.65,
                    "totalPrice": 101.29,
                    "installmentNumber": 2
                },
                {
                    "installmentPrice": 33.94,
                    "totalPrice": 101.82,
                    "installmentNumber": 3
                },
                {
                    "installmentPrice": 17.26,
                    "totalPrice": 103.55,
                    "installmentNumber": 6
                },
                {
                    "installmentPrice": 11.79,
                    "totalPrice": 106.15,
                    "installmentNumber": 9
                }
            ]
        }
    ]
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
Eğer istek yaparken “bin” numarası gönderilmez ise, tüm taksit seçenekleri dönmektedir. “Bin” numarası gönderilir ise, sadece o karta özel taksit seçenekleri dönmektedir.
{% endhint %}

{% code-tabs %}
{% code-tabs-item title="PHP" %}
```php
$request->setLocale(\Iyzipay\Model\Locale::TR);
$request->setConversationId("123456789");
$request->setBinNumber("554960");
$request->setPrice("100");

$installmentInfo = \Iyzipay\Model\InstallmentInfo::retrieve($request, Config::options());
```
{% endcode-tabs-item %}

{% code-tabs-item title="JAVA" %}
```java
RetrieveInstallmentInfoRequest request = new RetrieveInstallmentInfoRequest();
request.setLocale(Locale.TR.getValue());
request.setConversationId("123456789");
request.setBinNumber("554960");
request.setPrice(new BigDecimal("100"));

InstallmentInfo installmentInfo = InstallmentInfo.retrieve(request, options);
```
{% endcode-tabs-item %}
{% endcode-tabs %}

## Örnek Kodlar - Github

* [Php](https://github.com/iyzico/iyzipay-php/blob/master/samples/retrieve_installments.php#L1)
* [.Net](https://github.com/iyzico/iyzipay-dotnet/blob/master/Iyzipay.Samples/InstallmentSample.cs#L10)
* [Java](https://github.com/iyzico/iyzipay-java/blob/master/src/test/java/com/iyzipay/sample/InstallmentSample.java#L16)
* [Ruby](https://github.com/iyzico/iyzipay-ruby/blob/master/spec/installment_spec.rb#L13)
* [Python](https://github.com/iyzico/iyzipay-python/blob/master/samples/retrieve_installments.py#L12)
* [Node.js](https://github.com/iyzico/iyzipay-node/blob/master/samples/IyzipaySamples.js#L319)

