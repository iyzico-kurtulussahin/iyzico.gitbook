---
description: iyzico'da bir kullanıcıya ait kartları sorgulayabilirsiniz.
---

# Saklı Kartları Sorgulama

{% embed data="{\"url\":\"https://github.com/iyzico/iyzipay-php/blob/master/samples/retrieve\_cards.php\#L1\",\"type\":\"link\",\"title\":\"iyzico/iyzipay-php\",\"description\":\"iyzipay-php - iyzipay api php client\",\"icon\":{\"type\":\"icon\",\"url\":\"https://github.com/fluidicon.png\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://avatars2.githubusercontent.com/u/3815564?s=400&v=4\",\"width\":200,\"height\":200,\"aspectRatio\":1},\"caption\":\"Saklı kartları sorgulama Php örneği\"}" %}

{% hint style="info" %}
cardUserKey ile sorgu yapılır ve o cardUserKey altındaki cardToken değerlerini döner.
{% endhint %}

### Parametreler

{% tabs %}
{% tab title="İstek Parametreleri" %}
| **Parametre ismi** | **Tip** | **Zorunluluk** | **Açıklama** |
| :--- | :--- | :--- | :--- |
| **cardUserKey** | string | evet | Saklı kart kullanıcısının iyzico tarafından belirlenen değeri. |
| **locale** | string | hayır | iyzico istek sonucunda dönen metinlerin dilini ayarlamak için kullanılır. Varsayılan değeri tr’dir. |
| **conversationId** | string | hayır | İstek esnasında gönderip, sonuçta alabileceğiniz bir değer, request/response eşleşmesi yapmak için kullanılabilir. |
{% endtab %}

{% tab title="Dönüş Parametreleri" %}
| **Parametre ismi** | **Tip** | **Açıklama** |
| :--- | :--- | :--- |
| **status** | string | Yapılan isteğin sonucunu bildirir. İşlem başarılı ise **success**, hatalı ise **failure** döner. |
| **errorCode** | string | İşlem hatalıysa, bu hataya dair belirtilen koddur. |
| **errorMessage** | string | İşlem hatalıysa, bu hataya dair belirtilen mesajdır. Locale parametresine göre dil desteği sunar. |
| **errorGroup** | string | İşlem hatalıysa, bu hataya dair belirtilen gruptur. |
| **locale** | string | İstekte belirtilen locale değeri geri dönülür, varsayılan değeri **tr**dir. |
| **systemTime** | integer | Dönen sonucun o anki unix timestamp değeridir. |
| **conversationId** | string | İstek esnasında gönderilmişse, sonuçta aynen geri iletilir. |
| **carduserKey** | string | Saklı kart kullanıcısının iyzico tarafından belirlenen değeri. |
| **binNumber\(carddetails\)** | string | Kartın ilk 6 hanesidir. |
| **cardType\(carddetails\)** | string | Eğer ödeme yapılan kart yerel bir kart ise, kartın ait olduğu tipi. Geçerli değerler: CREDIT\_CARD, DEBIT\_CARD, PREPAID\_CARD |
| **cardAssociation\(carddetails\)** | string | Eğer ödeme yapılan kart yerel bir kart ise, kartın ait olduğu kuruluş. Geçerli değerler: VISA, MASTER\_CARD, AMERICAN\_EXPRESS |
| **cardFamily\(carddetails\)** | string | Eğer ödeme yapılan kart yerel bir kart ise, kartın ait olduğu aile. Geçerli değerler: Bonus, Axess, World, Maximum, Paraf, CardFinans. |
| **cardbankName\(carddetails\)** | string | Eğer ödeme yapılan kart yerel bir kart ise, kartın ait olduğu banka adı. |
| **cardbankCode\(carddetails\)** | integer | Eğer ödeme yapılan kart yerel bir kart ise, kartın ait olduğu banka kodu. |
| **cardtoken carddetails\)** | string | Saklı kart kullanıcısına bağlı iyzico tarafından belirlnen saklı kart değeri. |
| **cardalias\(carddetails\)** | string | Karta verilen isim. |
{% endtab %}

{% tab title="Örnek Resposne" %}
```text
{
    "status": "success",
    "locale": "tr",
    "systemTime": 1470731525201,
    "conversationId": "123456789",
    "cardUserKey": "W2OM/ZUXAn0qCepxpa5Taz89lV0=",
    "cardDetails": [
        {
            "cardToken": "nOwIOTbi5VShGNKXMSggEe4zcKQ=",
            "cardAlias": "card alias",
            "binNumber": "552879",
            "cardType": "CREDIT_CARD",
            "cardAssociation": "MASTER_CARD",
            "cardFamily": "Paraf",
            "cardBankCode": 12,
            "cardBankName": "Halk Bankası"
        },
        {
            "cardToken": "DAx+xnNEwm/4scO+ih7rOsM+4jo=",
            "cardAlias": "card alias",
            "binNumber": "552879",
            "cardType": "CREDIT_CARD",
            "cardAssociation": "MASTER_CARD",
            "cardFamily": "Paraf",
            "cardBankCode": 12,
            "cardBankName": "Halk Bankası"
        }
    ]
}
```
{% endtab %}
{% endtabs %}

### **Örnek Kodlar**

* [Php](https://github.com/iyzico/iyzipay-php/blob/master/samples/retrieve_cards.php#L1)
* [.Net](https://github.com/iyzico/iyzipay-dotnet/blob/master/Iyzipay.Samples/CardStorageSample.cs#L124)
* [Java](https://github.com/iyzico/iyzipay-java/blob/master/src/test/java/com/iyzipay/sample/CardStorageSample.java#L125)
* [Python](https://github.com/iyzico/iyzipay-python/blob/master/samples/retrieve_cards.py#L11)
* [Node.js](https://github.com/iyzico/iyzipay-node/blob/master/samples/IyzipaySamples.js#L217)

