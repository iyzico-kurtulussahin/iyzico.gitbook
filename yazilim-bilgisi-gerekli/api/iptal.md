---
description: Bankalar gün sonu almadan önce işlemin iptal edilmesidir.
---

# İptal

{% embed data="{\"url\":\"https://github.com/iyzico/iyzipay-php/blob/master/samples/cancel.php\#L1\",\"type\":\"link\",\"title\":\"iyzico/iyzipay-php\",\"description\":\"iyzipay-php - iyzipay api php client\",\"icon\":{\"type\":\"icon\",\"url\":\"https://github.com/fluidicon.png\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://avatars2.githubusercontent.com/u/3815564?s=400&v=4\",\"width\":200,\"height\":200,\"aspectRatio\":1},\"caption\":\"İptal sorgusu Php örneği\"}" %}

{% hint style="info" %}
iyzico üzerinden tahsil edilen bir ödeme, banka kuralları gereği aynı gün içinde \(gün sonu yapılmadan\) iptal \(cancel\) edilebilir.

İptal işleminin iadeden farkı, ödeme ile aynı gün yapılabilmesi ve kart ekstresinde girdi/çıktı yaratmamasıdır. 

İptal yapılabilmesi için ödemeye ait id \(paymentId\) gönderilmesi gerekir. İptal işlemi başarılıysa iptal edilen tutar \(price\) servisten döner. İptal işlemi tepeden çalışır, yani ödemenin tamamını iptal eder.  
{% endhint %}

### Parametreler





{% tabs %}
{% tab title="İstek Parametreleri" %}
| **Parametre ismi** | **Zorunluluk** |
| :--- | :--- |
| **ip** | evet |
| **paymentid** | evet |
| **locale** | hayır |
| **conversationId** | hayır |
{% endtab %}

{% tab title="Dönüş Parametreleri" %}
| **Parametre ismi** | **Tip** | **Açıklama** |
| :--- | :--- | :--- |
| **price** | string | Ödeme sepet tutarı. |
| **currency** | string | İptali yapılan ödeme para birimi. |
| **paymentid** | integer | iyzico tarafından işleme verilen benzersiz ödeme numarası. |
| **status** | string | Yapılan isteğin sonucunu bildirir. İşlem başarılı ise **success**, hatalı ise **failure** döner. |
| **errorCode** | string | İşlem hatalıysa, bu hataya dair belirtilen koddur. |
| **errorMessage** | string | İşlem hatalıysa, bu hataya dair belirtilen mesajdır. Locale parametresine göre dil desteği sunar. |
| **errorGroup** | string | İşlem hatalıysa, bu hataya dair belirtilen gruptur. |
| **locale** | string | İstekte belirtilen locale değeri geri dönülür, varsayılan değeri **tr** |
| ’dir. |  |  |
| **systemTime** | integer | Dönen sonucun o anki unix timestamp değeridir. |
| **conversationId** | string | İstek esnasında gönderilmişse, sonuçta aynen geri iletilir. |
{% endtab %}

{% tab title="Örnek Response" %}
```text
{  
   "status":"success",
   "locale":"tr",
   "systemTime":1527157939722,
   "conversationId":"123456789",
   "paymentId":"1",
   "price":1.20000000,
   "currency":"TRY",
   "authCode":"519468",
   "hostReference":"mock00007iyzihostrfn"
}
```
{% endtab %}
{% endtabs %}

### Örnek kodlar

* [Php](https://github.com/iyzico/iyzipay-php/blob/master/samples/cancel.php#L1)
* [.Net](https://github.com/iyzico/iyzipay-dotnet/blob/master/Iyzipay.Samples/CancelSample.cs#L10)
* [Java](https://github.com/iyzico/iyzipay-java/blob/master/src/test/java/com/iyzipay/sample/CancelSample.java#L14)
* [Ruby](https://github.com/iyzico/iyzipay-ruby/blob/master/spec/cancel_spec.rb#L13)
* [Python](https://github.com/iyzico/iyzipay-python/blob/master/samples/cancel.py#L11)
* [Node.js](https://github.com/iyzico/iyzipay-node/blob/master/samples/IyzipaySamples.js#L151)

