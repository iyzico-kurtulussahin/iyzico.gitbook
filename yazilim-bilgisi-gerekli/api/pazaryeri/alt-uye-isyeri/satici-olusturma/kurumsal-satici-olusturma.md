# Kurumsal Satıcı Oluşturma

{% embed data="{\"url\":\"https://github.com/iyzico/iyzipay-php/blob/master/samples/create\_sub\_merchant.php\#L55\",\"type\":\"link\",\"title\":\"iyzico/iyzipay-php\",\"description\":\"iyzipay-php - iyzipay api php client\",\"icon\":{\"type\":\"icon\",\"url\":\"https://github.com/fluidicon.png\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://avatars2.githubusercontent.com/u/3815564?s=400&v=4\",\"width\":200,\"height\":200,\"aspectRatio\":1}}" %}

{% hint style="info" %}
Pazaryeri satıcınız eğer Limited veya Anonim Şirket ise aşağıdaki input parametrelerini gönderip, Limited veya Anonim Şirket satıcılarınızın iyzico’ya kaydını sağlayabilirsiniz.
{% endhint %}

### Parametreler

{% tabs %}
{% tab title="İstek Parametreleri" %}
| **Parametre İsmi** | **Veri Tipi** | **Zorunlu** | **Açıklama** |
| :--- | :--- | :--- | :--- |
| **name** | String | Hayır | Alt üye işyeri adı. |
| **gsmNumber** | String | Hayır | Alt üye işyeri telefon numarası. |
| **taxOffice** | String | Evet | Alt üye işyeri vergi dairesi. |
| **taxNumber** | String | Evet | Alt üye işyeri vergi numarası. |
| **legalCompanyTitle** | String | Evet | Alt üye işyeri yasal şirket ünvanı. |
| **email** | String | Evet | Alt üye işyeri e-posta adresi. |
| **address** | String | Evet | Alt üye işyeri adresi. |
| **iban** | String | Hayır | Alt üye işyeri IBAN bilgisi. legalCompanyTitle ile uyumlu bir IBAN olmalı. Eğer alt üye işyeri ekleme esnasında boş bırakılırsa, ürüne onay vermeden önce mutlaka doldurulmalıdır. |
| **subMerchantExternalId** | String | Evet | Alt üye işyeri tekil dış ID’si, sizin sisteminizdeki ID olabilir. |
| **subMerchantType** | String | Evet | Limited veya Anonim Şirket için LIMITED\_OR\_JOINT\_STOCK\_COMPANY enum değeri gönderilmeli. |
{% endtab %}

{% tab title="Dönüş Parmetreleri" %}
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
    "systemTime": 1470732401915,
    "conversationId": "123456789",
    "subMerchantKey": "jsLbNEUu8XOKyxLdqqqqHUuu9bQ="
}
```
{% endtab %}
{% endtabs %}

### **Örnek Kodlar**

* [Php](https://github.com/iyzico/iyzipay-php/blob/master/samples/create_sub_merchant.php#L55)
* [.Net](https://github.com/iyzico/iyzipay-dotnet/blob/develop/Iyzipay.Samples/SubMerchantSample.cs#L72)
* [Java](https://github.com/iyzico/iyzipay-java/blob/master/src/test/java/com/iyzipay/sample/SubMerchantSample.java#L74)
* [Ruby](https://github.com/iyzico/iyzipay-ruby/blob/master/spec/sub_merchant_spec.rb#L63)
* [Python](https://github.com/iyzico/iyzipay-python/blob/master/samples/create_limited_company_sub_merchant.py)
* [Node.js](https://github.com/iyzico/iyzipay-node/blob/master/samples/IyzipaySamples.js#L769)

