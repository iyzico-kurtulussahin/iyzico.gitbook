# Ödeme Sorgulama

{% embed data="{\"url\":\"https://github.com/iyzico/iyzipay-php/blob/master/samples/retrieve\_payment\_result.php\#L1\",\"type\":\"link\",\"title\":\"iyzico/iyzipay-php\",\"description\":\"iyzipay-php - iyzipay api php client\",\"icon\":{\"type\":\"icon\",\"url\":\"https://github.com/fluidicon.png\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://avatars2.githubusercontent.com/u/3815564?s=400&v=4\",\"width\":200,\"height\":200,\"aspectRatio\":1},\"caption\":\"Ödeme sorgulama sorgusu Php örneği\"}" %}

### Parametreler

{% tabs %}
{% tab title="İstek parametreleri " %}
| **Parametre ismi** | **Tip** | **Zorunluluk** | **Açıklama** |
| :--- | :--- | :--- | :--- |
| **ip** | string | evet | İşlemin gönderildiği ip adresi. |
| **paymentId** | string | evet | iyzico tarafından işleme verilen benzersiz ödeme numarası. |
| **locale** | string | hayır | iyzico istek sonucunda dönen metinlerin dilini ayarlamak için kullanılır. Varsayılan değeri tr’dir. |
| **conversationId** | string | hayır | İstek esnasında gönderip, sonuçta alabileceğiniz bir değer, request/response eşleşmesi yapmak için kullanılabilir. |
| **paymentConversationId** | string | hayır | Üye işyeri tarafından işleme verilen benzersiz sipariş numarası. |
{% endtab %}

{% tab title="Dönüş parametreleri" %}
| **Parametre İsmi** | **Veri Tipi** | **Açıklama** |
| :--- | :--- | :--- |
| **status** | String | Yapılan isteğin sonucunu bildirir. İşlem başarılı ise success, hatalı ise failure döner. |
| **errorCode** | String | İşlem hatalıysa, bu hataya dair belirtilen koddur. |
| **errorMessage** | String | İşlem hatalıysa, bu hataya dair belirtilen mesajdır. Locale parametresine göre dil desteği sunar. |
| **errorGroup** | String | İşlem hatalıysa, bu hataya dair belirtilen gruptur. |
| **locale** | String | İstekte belirtilen locale değeri geri dönülür, varsayılan değeri tr’dir. |
| **systemTime** | Long | Dönen sonucun o anki unix timestamp değeridir. |
| **conversationId** | String | İstek esnasında gönderilmişse, sonuçta aynen geri iletilir. |
| **paymentId** | String | Ödemeye ait id, üye işyeri tarafından mutlaka saklanmalıdır. Ödemenin iptali ve iyzico ile iletişimde kullanılır. |
| **price** | Decimal | Ödeme sepet tutarı. Kırılım tutarlar toplamı sepet tutarına eşit olmalı. |
| **paidPrice** | Decimal | İndirim vade farkı vs. hesaplanmış POS’tan geçen, tahsil edilen, nihai tutar. |
| **currency** | String | Ödemenin alındığı para birimi. |
| **installment** | Integer | Ödemenin taksit bilgisi, tek çekim için 1 döner. Geçerli değerler: 1, 2, 3, 6, 9, 12. |
| **paymentStatus** | String | İşlemin sonucunu gösterir. Geçerli değerler SUCCESS, FAILURE, INIT\_THREEDS, CALLBACK\_THREEDS, BKM\_POS\_SELECTED, CALLBACK\_PECCO |
| **basketId** | String | Üye işyeri tarafından gönderilen sepet id’si. |
| **binNumber** | String | Ödeme yapılan kartın ilk 6 hanesi. |
| **cardAssociation** | String | Eğer ödeme yapılan kart yerel bir kart ise, kartın ait olduğu kuruluş. Geçerli değerler: VISA, MASTER\_CARD, AMERICAN\_EXPRESS, TROY |
| **cardFamily** | String | Eğer ödeme yapılan kart yerel bir kart ise, kartın ait olduğu aile. Geçerli değerler: Bonus, Axess, World, Maximum, Paraf, CardFinans, Advantage |
| **cardType** | String | Eğer ödeme yapılan kart yerel bir kart ise, kartın ait olduğu tipi. Geçerli değerler: CREDIT\_CARD, DEBIT\_CARD, PREPAID\_CARD |
| **fraudStatus** | Integer | Ödeme işleminin fraud filtrelerine göre durumu. Eğer ödemenin fraud risk skoru düşük ise ödemeye anında onay verilir, bu durumda 1 değeri döner. Eğer fraud risk skoru yüksek ise ödeme işlemi reddedilir ve -1 döner. Eğer ödeme işlemi daha sonradan incelenip karar verilecekse 0 döner. Geçerli değerler: 0, -1 ve 1. Üye işyeri sadece 1 olan işlemlerde ürünü kargoya vermelidir, 0 olan işlemler için bilgilendirme beklemelidir. |
| **iyziCommissionFee** | Decimal | Ödemeye ait iyzico işlem ücreti. |
| **iyziCommissionRateAmount** | Decimal | Ödemeye ait iyzico işlem komisyon tutarı. |
| **merchantCommissionRate** | Decimal | Üye işyerinin uyguladığı vade/komisyon oranı. Örneğin price=100, paidPrice=110 ise üye işyeri vade/komisyon oranı %10’dur. Bilgi amaçlıdır. |
| **merchantCommissionRateAmount** | Decimal | Üye işyerinin uyguladığı vade/komisyon tutarı. Örneğin price=100, paidPrice=110 ise üye işyeri vade/komisyon tutarı 10’dur. Bilgi amaçlıdır. |
| **paymentTransactionId \(ItemTransactions\)** | String | Ödeme kırılımına ait id, üye işyeri tarafından mutlaka saklanmalıdır. Ödeme kırılımının iadesi, onayı, onay geri çekmesi ve iyzico ile iletişimde kullanılır. Tercihen itemId ile ilişkili bir şekilde tutulmalıdır. |
| **itemId\(ItemTransactions\)** | String | Üye işyeri tarafından iletilen, sepetteki ürüne ait id. |
| **price\(ItemTransactions\)** | Decimal | Üye işyeri tarafındaki sepetteki ürüne ait tutar. |
| **paidPrice\(ItemTransactions\)** | Decimal | Tahsilat tutarının kırılım bazındaki dağılımı. Üye işyeri tarafından mutlaka saklanmalıdır. |
| **transactionStatus \(ItemTransactions\)** | Integer | Ödeme kırılımının durumu. Ödeme fraud kontrolünde ise 0 değeri döner, bu durumda fraudStatus değeri de 0’dır. Ödeme, fraud kontrolünden sonra reddedilirse -1 döner. Pazaryeri modelinde ürüne onay verilene dek bu değer 1 olarak döner. Pazaryeri modelinde ürüne onay verilmişse bu değer 2 olur. Geçerli değerler: 0, -1, 1, 2. |
| **blockageRate\(ItemTransactions\)** | Decimal | Kırılım bazında üye işyeri blokaj oranı. iyzico – üye işyeri anlaşmasına göre, üye işyerine işlem bazında blokaj uygulayabilir. Bu blokaj üye işyeri fraud riskini önlemek içindir, blokaj süresi boyunca para iyzico’da tutulur, bu süre sonrasında üye işyerine gönderilir. |
| **blockageRateAmountMerchant\(ItemTransactions\)** | Decimal | Kırılım bazında üye işyeri blokaj tutarının, üye işyerine yansıyan rakamı. Blokaj tutarı mümkün olduğunca üye işyerine yansıtılır. Eğer blokaj tutarı, üye işyeri tutarından daha büyükse bu durumda alt üye işyerine de yansıtılır. |
| **blockageResolvedDate\(ItemTransactions\)** | String | İşlem bazında blokaj çözülme tarihi. yyyy-MM-dd HH:mm:ss formatındadır, örneğin 2015-10-19 14:36:52. |
| **iyziCommissionFee\(ItemTransactions\)** | Decimal | iyzico işlem ücretinin kırılım bazında dağılmış tutarı. |
| **iyziCommissionRateAmount\(ItemTransactions\)** | Decimal | iyzico işlem komisyon tutarının kırılım bazında dağılmış tutarı. |
| **merchantCommissionRate\(ItemTransactions\)** | Decimal | Üye işyerinin uyguladığı vade/komisyon oranının kırılım bazında dağılmış oranı. |
| **merchantCommissionRateAmount\(ItemTransactions\)** | Decimal | Üye işyerinin uyguladığı vade/komisyon tutarıın, kırılım bazında dağılmış tutarı. |
| **merchantPayoutAmount\(ItemTransactions\)** | Decimal | Bu kırılım için, iyzico işlem ücreti, komisyon tutarı ve blokajlar düşüldükten sonra üye işyerine gönderilecek tutar. |
| **paidPrice\(ItemTransactions\)\(convertedPayout\)** | Decimal | Tahsilat tutarının kırılım bazındaki dağılımı. Üye işyeri tarafından mutlaka saklanmalıdır. |
| **iyziCommissionFee\(ItemTransactions\)\(convertedPayout\)** | Decimal | iyzico işlem ücretinin kırılım bazında dağılmış tutarı. |
| **iyziCommissionRateAmount\(ItemTransactions\)\(convertedPayout\)** | Decimal | iyzico işlem komisyon tutarının kırılım bazında dağılmış tutarı. |
| **blockageRateAmountMerchant\(ItemTransactions\)\(convertedPayout\)** | Decimal | Kırılım bazında üye işyeri blokaj tutarının, üye işyerine yansıyan rakamı. Blokaj tutarı mümkün olduğunca üye işyerine yansıtılır. Eğer blokaj tutarı, üye işyeri tutarından daha büyükse bu durumda alt üye işyerine de yansıtılır. |
| **merchantPayoutAmount\(ItemTransactions\)\(convertedPayout\)** | Decimal | Bu kırılım için, iyzico işlem ücreti, komisyon tutarı ve blokajlar düşüldükten sonra üye işyerine gönderilecek tutar. |
| **iyziConversationRate\(ItemTransactions\)\(convertedPayout\)** | Decimal | Bu kırılım için, iyzico işlem ücreti, komisyon tutarı ve blokajlar düşüldükten sonra üye işyerine gönderilecek tutar. |
| **iyziConversationRateAmount\(ItemTransactions\)\(convertedPayout\)** | Decimal | Bu kırılım için, iyzico işlem ücreti, komisyon tutarı ve blokajlar düşüldükten sonra üye işyerine gönderilecek tutar. |
| **currency\(ItemTransactions\)\(convertedPayout\)** | String | Ödemenin alındığı para birimi. |
{% endtab %}

{% tab title="Örnek response" %}
```text
{
   "status":"success",
   "paymentStatus":"SUCCESS",
   "locale":"TR",
   "systemTime":1498125169531,
   "conversationId":"123456789",
   "price":1,
   "paidPrice":1.5,
   "installment":1,
   "paymentId":"1",
   "fraudStatus":1,
   "merchantCommissionRate":50,
   "merchantCommissionRateAmount":0.5,
   "iyziCommissionRateAmount":0.039375,
   "iyziCommissionFee":0.25,
   "cardType":"CREDIT_CARD",
   "cardAssociation":"MASTER_CARD",
   "cardFamily":"Bonus",
   "binNumber":"540036",
   "lastFourDigits":"0003",
   "basketId":"B67832",
   "currency":"TRY",
   "itemTransactions":[
      {
         "itemId":"BI101",
         "paymentTransactionId":"666861",
         "transactionStatus":2,
         "price":0.3,
         "paidPrice":0.45,
         "merchantCommissionRate":50,
         "merchantCommissionRateAmount":0.15,
         "iyziCommissionRateAmount":0.0118125,
         "iyziCommissionFee":0.075,
         "blockageRate":0,
         "blockageRateAmountMerchant":0,
         "blockageRateAmountSubMerchant":0,
         "blockageResolvedDate":"2017-06-22 12:52:49",
         "subMerchantPrice":0,
         "subMerchantPayoutRate":0,
         "subMerchantPayoutAmount":0,
         "merchantPayoutAmount":0.3631875,
         "convertedPayout":{
            "paidPrice":0.45,
            "iyziCommissionRateAmount":0.0118125,
            "iyziCommissionFee":0.075,
            "blockageRateAmountMerchant":0,
            "blockageRateAmountSubMerchant":0,
            "subMerchantPayoutAmount":0,
            "merchantPayoutAmount":0.3631875,
            "iyziConversionRate":0,
            "iyziConversionRateAmount":0,
            "currency":"TRY"
         }
      },
      {
         "itemId":"BI102",
         "paymentTransactionId":"666862",
         "transactionStatus":2,
         "price":0.5,
         "paidPrice":0.75,
         "merchantCommissionRate":50,
         "merchantCommissionRateAmount":0.25,
         "iyziCommissionRateAmount":0.0196875,
         "iyziCommissionFee":0.125,
         "blockageRate":0,
         "blockageRateAmountMerchant":0,
         "blockageRateAmountSubMerchant":0,
         "blockageResolvedDate":"2017-06-22 12:52:49",
         "subMerchantPrice":0,
         "subMerchantPayoutRate":0,
         "subMerchantPayoutAmount":0,
         "merchantPayoutAmount":0.6053125,
         "convertedPayout":{
            "paidPrice":0.75,
            "iyziCommissionRateAmount":0.0196875,
            "iyziCommissionFee":0.125,
            "blockageRateAmountMerchant":0,
            "blockageRateAmountSubMerchant":0,
            "subMerchantPayoutAmount":0,
            "merchantPayoutAmount":0.6053125,
            "iyziConversionRate":0,
            "iyziConversionRateAmount":0,
            "currency":"TRY"
         }
      },
      {
         "itemId":"BI103",
         "paymentTransactionId":"666863",
         "transactionStatus":2,
         "price":0.2,
         "paidPrice":0.3,
         "merchantCommissionRate":50,
         "merchantCommissionRateAmount":0.1,
         "iyziCommissionRateAmount":0.007875,
         "iyziCommissionFee":0.05,
         "blockageRate":0,
         "blockageRateAmountMerchant":0,
         "blockageRateAmountSubMerchant":0,
         "blockageResolvedDate":"2017-06-22 12:52:49",
         "subMerchantPrice":0,
         "subMerchantPayoutRate":0,
         "subMerchantPayoutAmount":0,
         "merchantPayoutAmount":0.242125,
         "convertedPayout":{
            "paidPrice":0.3,
            "iyziCommissionRateAmount":0.007875,
            "iyziCommissionFee":0.05,
            "blockageRateAmountMerchant":0,
            "blockageRateAmountSubMerchant":0,
            "subMerchantPayoutAmount":0,
            "merchantPayoutAmount":0.242125,
            "iyziConversionRate":0,
            "iyziConversionRateAmount":0,
            "currency":"TRY"
         }
      }
   ],
   "authCode":"mock00008iyziauthcd",
   "phase":"AUTH"
}
```
{% endtab %}
{% endtabs %}

### Örnek kodlar

* [Php](https://github.com/iyzico/iyzipay-php/blob/master/samples/retrieve_payment_result.php#L1)
* [.Net](https://github.com/iyzico/iyzipay-dotnet/blob/master/Iyzipay.Samples/PaymentSample.cs#L304)
* [Java](https://github.com/iyzico/iyzipay-java/blob/master/src/test/java/com/iyzipay/sample/PaymentSample.java#L307)
* [Ruby](https://github.com/iyzico/iyzipay-ruby/blob/master/spec/payment_spec.rb#L262)
* [Python](https://github.com/iyzico/iyzipay-python/blob/master/samples/retrieve_payment_result.py#L11)
* [Node.js](https://github.com/iyzico/iyzipay-node/blob/master/samples/IyzipaySamples.js#L582)

