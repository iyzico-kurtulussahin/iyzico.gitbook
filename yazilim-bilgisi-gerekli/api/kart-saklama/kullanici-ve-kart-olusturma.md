---
description: >-
  Bu servisi kullanarak ödeme oluşturmadan, iyzico'da bir kullanıcı ve o
  kullanıcıya bağlı bir kart oluşturabilirsiniz.
---

# Kullanıcı ve Kart Oluşturma

{% embed data="{\"url\":\"https://github.com/iyzico/iyzipay-php/blob/master/samples/create\_card.php\#L5\",\"type\":\"link\",\"title\":\"iyzico/iyzipay-php\",\"description\":\"iyzipay-php - iyzipay api php client\",\"icon\":{\"type\":\"icon\",\"url\":\"https://github.com/fluidicon.png\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://avatars2.githubusercontent.com/u/3815564?s=400&v=4\",\"width\":200,\"height\":200,\"aspectRatio\":1},\"caption\":\"Kullanıcı ve kart oluşturma sorgusu Php örneği\"}" %}

{% hint style="info" %}
Sorgu cevabındaki **carduserkey** ve **cardtoken** değerleri saklanan kartı temsil etmektedir ve ödeme isteğinde kart bilgisi yerine kullanılır.
{% endhint %}

### Parametreler

{% tabs %}
{% tab title="İstek Parametreleri" %}
| **Parametre ismi** | **Tip** | **Zorunluluk** | **Açıklama** |
| :--- | :--- | :--- | :--- |
| **cardAlias** | string | evet | Saklı karta verilen isim. |
| **cardHoldername** | string | evet | Kartın üzerindeki isim. |
| **cardNumber** | string | evet | Kartın numarası. |
| **expireMonth** | string | evet | Kartın üzerindeki ay. |
| **expireYear** | string | evet | Kartın üzerindeki yıl. |
| **email** | string | evet | Saklı kart sahibinin email adresi. |
| **externalId** | string | hayır | Saklanmak istenen karta üye iş yeri tarafından verilen id. |
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
| **binNumber** | string | Kartın ilk 6 hanesidir. |
| **cardType** | string | Eğer ödeme yapılan kart yerel bir kart ise, kartın ait olduğu tipi. Geçerli değerler: CREDIT\_CARD, DEBIT\_CARD, PREPAID\_CARD |
| **cardAssociation** | string | Eğer ödeme yapılan kart yerel bir kart ise, kartın ait olduğu kuruluş. Geçerli değerler: VISA, MASTER\_CARD, AMERICAN\_EXPRESS |
| **cardFamily** | string | Eğer ödeme yapılan kart yerel bir kart ise, kartın ait olduğu aile. Geçerli değerler: Bonus, Axess, World, Maximum, Paraf, CardFinans. |
| **cardBankName** | string | Eğer ödeme yapılan kart yerel bir kart ise, kartın ait olduğu banka adı. |
| **cardBankCode** | integer | Eğer ödeme yapılan kart yerel bir kart ise, kartın ait olduğu banka kodu. |
| **email** | string | Saklanan kart üzerindeki email. |
| **cardUserKey** | string | Saklı kart kullanıcısının iyzico tarafından belirlenen değeri. |
| **cardToken** | string | Saklı kart kullanıcısına bağlı iyzico tarafından belirlenen saklı kart değeri. |
| **cardAlias** | string | Karta verilen isim. |
{% endtab %}

{% tab title="Örnek Response" %}
```text
{
   "status":"success",
   "locale":"tr",
   "systemTime":1470731323108,
   "conversationId":"123456789",
   "externalId":"external id",
   "email":"email@email.com",
   "cardUserKey":"W2OM/ZUXAn0qCepxpa5Taz89lV0=",
   "cardToken":"nOwIOTbi5VShGNKXMSggEe4zcKQ=",
   "cardAlias":"card alias",
   "binNumber":"552879",
   "cardType":"CREDIT_CARD",
   "cardAssociation":"MASTER_CARD",
   "cardFamily":"Paraf",
   "cardBankCode":12,
   "cardBankName":"Halk Bankası"
}
```
{% endtab %}
{% endtabs %}

### **Örnek Kodlar**

* [Php](https://github.com/iyzico/iyzipay-php/blob/master/samples/create_card.php#L5)
* [.Net](https://github.com/iyzico/iyzipay-dotnet/blob/master/Iyzipay.Samples/CardStorageSample.cs#L10)
* [Java](https://github.com/iyzico/iyzipay-java/blob/master/src/test/java/com/iyzipay/sample/CardStorageSample.java#L14)
* [Python](https://github.com/iyzico/iyzipay-python/blob/master/samples/create_user_and_card.py#L11)
* [Node.js](https://github.com/iyzico/iyzipay-node/blob/master/samples/IyzipaySamples.js#L168)

