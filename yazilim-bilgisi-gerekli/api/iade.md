# İade

iyzico üzerinden tahsil edilen bir ödeme, 365 gün 7/24 iade \(refund\) edilebilir. İade işlemi mutlaka ekstreye yansır ve iade edilen ödeme taksitli bir işlemse, iadenin karta yansıması bankadan bankaya değişmekle beraber birkaç günü bulabilir. İade işlemi kırılımdan çalışır, yani ödemenin bir kırılımının tamamını veya bir kısmını iade eder.

{% hint style="info" %}
İade yapılabilmesi için ödeme kırılımına ait id\(paymentTransactionId\) ve iade edilecek tutar\(price\) gönderilmesi gerekir. İade işlemi başarılıysa, iade edilen tutar\(price\) servisten döner. İade edilecek tutar\(price\), iade edilecek ödemenin kırılımının tutarından\(itemTransaction -&gt; paidPrice\) ve iade edilebilir kalan tutardan küçük veya eşit olmalıdır. Bu kural sağlandığı sürece ardarda defalarca iade yapılabilir.
{% endhint %}

### Parametreler

{% tabs %}
{% tab title="İstek parametreleri" %}
| **Parametre ismi** | **Tip** | **Zorunluluk** | **Açıklama** |
| :--- | :--- | :--- | :--- |
| **ip** | string | evet | İşlemin gönderildiği ip adresi. |
| **price** | string | evet | İade edilmek istenen tutar. |
| **paymentTransactionId** | string | evet | iyzico tarafından işleme verilen benzersiz ödeme kırılım numarası. |
| **locale** | string | hayır | iyzico istek sonucunda dönen metinlerin dilini ayarlamak için kullanılır. Varsayılan değeri tr’dir. |
| **conversationId** | string | hayır | İstek esnasında gönderip, sonuçta alabileceğiniz bir değer, request/response eşleşmesi yapmak için kullanılabilir. |
{% endtab %}

{% tab title="Dönüş parametreleri" %}
| **Parametre ismi** | **Tip** | **Açıklama** |
| :--- | :--- | :--- |
| **price** | string | İade edilen tutar. |
| **currency** | string | İptali yapılan ödeme para birimi. |
| **paymentid** | integer | iyzico tarafından işleme verilen benzersiz ödeme numarası. |
| **paymentTransactionId** | string | iyzico tarafından işleme verilen benzersiz ödeme kırılım numarası. |
| **status** | string | Yapılan isteğin sonucunu bildirir. İşlem başarılı ise **success**, hatalı ise **failure** döner. |
| **errorCode** | string | İşlem hatalıysa, bu hataya dair belirtilen koddur. |
| **errorMessage** | string | İşlem hatalıysa, bu hataya dair belirtilen mesajdır. Locale parametresine göre dil desteği sunar. |
| **errorGroup** | string | İşlem hatalıysa, bu hataya dair belirtilen gruptur. |
| **locale** | string | İstekte belirtilen locale değeri geri dönülür, varsayılan değeri **tr**’dir. |
| **systemTime** | integer | Dönen sonucun o anki unix timestamp değeridir. |
| **conversationId** | string | İstek esnasında gönderilmişse, sonuçta aynen geri iletilir. |
{% endtab %}

{% tab title="Örnek response" %}
```text
{
   "status":"success",
   "locale":"tr",
   "systemTime":1527959985667,
   "conversationId":"123456789",
   "paymentId":"10844367",
   "paymentTransactionId":"11433038",
   "price":0.5,
   "currency":"TRY",
   "authCode":"475990",
   "hostReference":"mock00007iyzihostrfn"
}
```
{% endtab %}
{% endtabs %}

### Örnek kodlar

* [Php](https://github.com/iyzico/iyzipay-php/blob/master/samples/refund.php#L1)
* [.Net](https://github.com/iyzico/iyzipay-dotnet/blob/master/Iyzipay.Samples/RefundSample.cs#L10)
* [Java](https://github.com/iyzico/iyzipay-java/blob/master/src/test/java/com/iyzipay/sample/RefundSample.java#L17)
* [Ruby](https://github.com/iyzico/iyzipay-ruby/blob/master/spec/refund_spec.rb#L13)
* [Python](https://github.com/iyzico/iyzipay-python/blob/master/samples/refund.py#L11)
* [Node.js](https://github.com/iyzico/iyzipay-node/blob/master/samples/IyzipaySamples.js#L683)

