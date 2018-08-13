# Şahıs Şirketi Satıcı Oluşturma

{% embed data="{\"url\":\"https://github.com/iyzico/iyzipay-php/blob/master/samples/create\_sub\_merchant.php\#L30\",\"type\":\"link\",\"title\":\"iyzico/iyzipay-php\",\"description\":\"iyzipay-php - iyzipay api php client\",\"icon\":{\"type\":\"icon\",\"url\":\"https://github.com/fluidicon.png\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://avatars2.githubusercontent.com/u/3815564?s=400&v=4\",\"width\":200,\"height\":200,\"aspectRatio\":1}}" %}

{% hint style="info" %}
Pazaryeri satıcınız eğer Şahıs firması ise aşağıdaki input parametrelerini gönderip, Şahıs Şirketi satıcılarınızın iyzico’ya kaydını sağlayabilirsiniz.
{% endhint %}

### Parametreler

{% tabs %}
{% tab title="İstek Parametreleri" %}
| **Parametre İsmi** | **Veri Tipi** | **Zorunlu** | **Açıklama** |
| :--- | :--- | :--- | :--- |
| **name** | String | Hayır | Alt üye işyeri adı. |
| **gsmNumber** | String | Hayır | Alt üye işyeri telefon numarası. |
| **taxOffice** | String | Evet | Alt üye işyeri vergi dairesi. |
| **legalCompanyTitle** | String | Evet | Alt üye işyeri yasal şirket ünvanı. |
| **email** | String | Evet | Alt üye işyeri e-posta adresi. |
| **address** | String | Evet | Alt üye işyeri adresi. |
| **iban** | String | Hayır | Alt üye işyeri IBAN bilgisi. legalCompanyTitle ile uyumlu bir IBAN olmalı. Eğer alt üye işyeri ekleme esnasında boş bırakılırsa, ürüne onay vermeden önce mutlaka doldurulmalıdır. |
| **subMerchantExternalId** | String | Evet | Alt üye işyeri tekil dış ID’si, sizin sisteminizdeki ID olabilir. |
| **identityNumber** | String | Hayır | Alt üye işyeri T.C. kimlik numarası. Eğer alt üye işyeri ekleme esnasında boş bırakılırsa, ürüne onay vermeden önce mutlaka doldurulmalıdır. |
| **subMerchantType** | String | Evet | Şahıs Şirketi için PRIVATE\_COMPANY enum değeri gönderilmeli. |
{% endtab %}

{% tab title="Dönüş Parametreleri" %}
| **Parametre ismi** | **Tip** | **Açıklama** |
| :--- | :--- | :--- |
| **subMerchantKey** | String | Alt üye işyerini simgeleyen tekil değer. |
| **status** | string | Yapılan isteğin sonucunu bildirir. İşlem başarılı ise **success**, hatalı ise **failure** döner. |
| **errorCode** | string | İşlem hatalıysa, bu hataya dair belirtilen koddur. |
| **errorMessage** | string | İşlem hatalıysa, bu hataya dair belirtilen mesajdır, locale parametresine göre dil desteği sunar. |
| **errorGroup** | string | İşlem hatalıysa, bu hataya dair belirtilen gruptur. |
| **locale** | string | İstekte belirtilen locale değeri geri dönülür, varsayılan değeri **tr**’dir. |
| **systemTime** | integer | Dönen sonucun o anki unix timestamp değeridir. |
| **conversationId** | string | İstek esnasında gönderilmişse, sonuçta aynen geri iletilir. |
{% endtab %}

{% tab title="Örnek Response" %}
```text
{
    "status": "success",
    "locale": "tr",
    "systemTime": 1470732341410,
    "conversationId": "123456789",
    "subMerchantKey": "PPFFZPedVQSvaOqZu5xpvpLEqmc="
}
```
{% endtab %}
{% endtabs %}

### **Örnek Kodlar**

* [Php](https://github.com/iyzico/iyzipay-php/blob/master/samples/create_sub_merchant.php#L30)
* [.Net](https://github.com/iyzico/iyzipay-dotnet/blob/master/Iyzipay.Samples/SubMerchantSample.cs#L41)
* [Java](https://github.com/iyzico/iyzipay-java/blob/master/src/test/java/com/iyzipay/sample/SubMerchantSample.java#L44)
* [Ruby](https://github.com/iyzico/iyzipay-ruby/blob/master/spec/sub_merchant_spec.rb#L38)
* [Python](https://github.com/iyzico/iyzipay-python/blob/master/samples/create_private_sub_merchant.py#L11)
* [Node.js](https://github.com/iyzico/iyzipay-node/blob/master/samples/IyzipaySamples.js#L748)

