# Kurumsal Satıcı Günelleme

{% embed data="{\"url\":\"https://github.com/iyzico/iyzipay-php/blob/master/samples/update\_sub\_merchant.php\#L53\",\"type\":\"link\",\"title\":\"iyzico/iyzipay-php\",\"description\":\"iyzipay-php - iyzipay api php client\",\"icon\":{\"type\":\"icon\",\"url\":\"https://github.com/fluidicon.png\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://avatars2.githubusercontent.com/u/3815564?s=400&v=4\",\"width\":200,\"height\":200,\"aspectRatio\":1}}" %}

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
| **iban** | String | Evet | Alt üye işyeri IBAN bilgisi. legalCompanyTitle ile uyumlu bir IBAN olmalı. |
| **subMerchantKey** | String | Evet | Güncellenmek isteyen alt üye işyerinin anahtarı. |
{% endtab %}

{% tab title="Dönüş Parametreleri" %}
| **Parametre ismi** | **Tip** | **Açıklama** |
| :--- | :--- | :--- |
| **status** | string | Yapılan isteğin sonucunu bildirir. İşlem başarılı ise **success**, hatalı ise **failure** döner. |
| **errorCode** | string | İşlem hatalıysa, bu hataya dair belirtilen koddur. |
| **errorMessage** | string | İşlem hatalıysa, bu hataya dair belirtilen mesajdır, locale parametresine göre dil desteği sunar. |
| **errorGroup** | string | İşlem hatalıysa, bu hataya dair belirtilen gruptur. |
| **locale** | string | İstekte belirtilen locale değeri geri dönülür, varsayılan değeri **tr**’dir. |
| **systemTime** | integer | Dönen sonucun o anki unix timestamp değeridir. |
| **conversationId** | string | İstek esnasında gönderilmişse, sonuçta aynen geri iletilir. |
{% endtab %}

{% tab title="Örnek Respınse" %}
```text
{
    "status": "success",
    "locale": "tr",
    "systemTime": 1470733009785,
    "conversationId": "123456789"
}
```
{% endtab %}
{% endtabs %}

### **Örnek Kodlar**

* [Php](https://github.com/iyzico/iyzipay-php/blob/develop/samples/update_sub_merchant.php#L53)
* [.Net](https://github.com/iyzico/iyzipay-dotnet/blob/master/Iyzipay.Samples/SubMerchantSample.cs#L163)
* [Java](https://github.com/iyzico/iyzipay-java/blob/develop/src/test/java/com/iyzipay/sample/SubMerchantSample.java#L162)
* [Ruby](https://github.com/iyzico/iyzipay-ruby/blob/develop/spec/sub_merchant_spec.rb#L138)
* [Python](https://github.com/iyzico/iyzipay-python/blob/master/samples/update_limited_company_sub_merchant.py)
* [Node.js](https://github.com/iyzico/iyzipay-node/blob/develop/samples/IyzipaySamples.js#L830)

