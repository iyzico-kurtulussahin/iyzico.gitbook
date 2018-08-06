---
description: >-
  3d sürecinin, güvenlik onayından sonraki karttan para çekilme işlemininin
  yapıldığı 2. adımıdır.
---

# 3d Tamamlama

3ds tamamlama sorgusunda; istek parametreleri için, [callbackurl adresinize gönderilen parametr](https://iyzico.gitbook.io/tr/yazilim-bilgisi-gerekli/api/untitled/3d-baslatma#callbackurl-adresine-post-edilen-degerler)eleri kullanmalısınız. 

{% hint style="info" %}
Öncelikle [3ds Akışı](https://iyzico.gitbook.io/tr/yazilim-bilgisi-gerekli/api/untitled/3d-baslatma#3ds-akisi) hakkındaki açıklamaları okumayı unutmayınız.
{% endhint %}

{% embed data="{\"url\":\"https://github.com/iyzico/iyzipay-php/blob/master/samples/create\_threeds\_payment.php\#L1\",\"type\":\"link\",\"title\":\"iyzico/iyzipay-php\",\"description\":\"iyzipay-php - iyzipay api php client\",\"icon\":{\"type\":\"icon\",\"url\":\"https://github.com/fluidicon.png\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://avatars2.githubusercontent.com/u/3815564?s=400&v=4\",\"width\":200,\"height\":200,\"aspectRatio\":1},\"caption\":\"3d başlatma sorgusu Php örneği\"}" %}

### Parametreler

{% tabs %}
{% tab title="İstek Parametreleri " %}
| **Parametre ismi** | **Tip** | **Zorunluluk** | **Açıklama** |
| :--- | :--- | :--- | :--- |
| **locale** | string | hayır | iyzico istek sonucunda dönen metinlerin dilini ayarlamak için kullanılır. Varsayılan değeri tr’dir. |
| **conversationId** | string | hayır | İstek esnasında gönderip, sonuçta alabileceğiniz bir değer, request/response eşleşmesi yapmak için kullanılabilir. |
| **paymentId** | string | evet | 3D dönüş bağlantı adresinizden alacağınız paymentid değeridir. |
| **conversationData** | string | hayır | 3D dönüş bağlantı adresinizden alacağınız conversationData değeridir. Bu parametre bir değer ile dönüş yapmış ise 3D ödeme sorgusunda eklenmelidir. |
{% endtab %}

{% tab title="Dönüş Parametreleri" %}
| **Parametre İsmi** | **Veri Tipi** | **Açıklama** |
| :--- | :--- | :--- |
| **status** | String | Yapılan isteğin sonucunu bildirir. İşlem başarılı ise success, hatalı ise failure döner. |
| **errorCode** | String | İşlem hatalıysa, bu hataya dair belirtilen koddur. |
| **errorMessage** | String | İşlem hatalıysa, bu hataya dair belirtilen mesajdır, locale parametresine göre dil desteği sunar. |
| **errorGroup** | String | İşlem hatalıysa, bu hataya dair belirtilen gruptur. |
| **locale** | String | İstekte belirtilen locale değeri geri dönülür, varsayılan değeri tr’dir. |
| **systemTime** | Long | Dönen sonucun o anki unix timestamp değeridir. |
| **conversationId** | String | İstek esnasında gönderilmişse, sonuçta aynen geri iletilir. |
| **paymentId** | String | Ödemeye ait id, üye işyeri tarafından mutlaka saklanmalıdır. Ödemenin iptali ve iyzico ile iletişimde kullanılır. |
| **price** | Decimal | Ödeme sepet tutarı. Kırılım tutarlar toplamı, sepet tutarına eşit olmalı. |
| **paidPrice** | Decimal | İndirim vade farkı vs. hesaplanmış POS’tan geçen, tahsil edilen, nihai tutar. |
| **currency** | String | Ödemenin alındığı para birimi. |
| **installment** | Integer | Ödemenin taksit bilgisi, tek çekim için 1 döner. Geçerli değerler: **1**, **2**, **3**, **6**, **9**. |
| **basketId** | String | Üye işyeri tarafından gönderilen sepet id’si. |
| **binNumber** | String | Ödeme yapılan kartın ilk 6 hanesi. |
| **cardAssociation** | String | Eğer ödeme yapılan kart yerel bir kart ise, kartın ait olduğu kuruluş. Geçerli değerler: VISA, MASTER\_CARD, AMERICAN\_EXPRESS, TROY |
| **cardFamily** | String | Eğer ödeme yapılan kart yerel bir kart ise, kartın ait olduğu aile. Geçerli değerler: Bonus, Axess, World, Maximum, Paraf, CardFinans, Advantage. |
| **cardType** | String | Eğer ödeme yapılan kart yerel bir kart ise, kartın ait olduğu tipi. Geçerli değerler: CREDIT\_CARD, DEBIT\_CARD, PREPAID\_CARD. |
| **fraudStatus** | Integer | Ödeme işleminin fraud filtrelerine göre durumu. Eğer ödemenin fraud risk skoru düşük ise ödemeye anında onay verilir bu durumda 1 değeri döner. Eğer fraud risk skoru yüksek ise ödeme işlemi reddedilir ve -1 döner. Eğer ödeme işlemi daha sonradan incelenip karar verilecekse 0 döner. Geçerli değerler: 0, -1 ve 1. Üye işyeri sadece 1 olan işlemlerde ürünü kargoya vermelidir, 0 olan işlemler için bilgilendirme beklenmelidir. |
| **iyziCommissionFee** | Decimal | Ödemeye ait iyzico işlem ücreti. |
| **iyziCommissionRateAmount** | Decimal | Ödemeye ait iyzico işlem komisyon tutarı. |
| **merchantCommissionRate** | Decimal | Üye işyerinin uyguladığı vade/komisyon oranı. Örneğin price=100, paidPrice=110 ise üye işyeri vade/komisyon oranı %10’dur. Bilgi amaçlıdır. |
| **merchantCommissionRateAmount** | Decimal | Üye işyerinin uyguladığı vade/komisyon tutarı. Örneğin price=100, paidPrice=110 ise üye işyeri vade/komisyon tutarı 10’dur. Bilgi amaçlıdır. |
| **paymentTransactionId \(ItemTransactions\)** | String | Ödeme kırılımına ait id, üye işyeri tarafından mutlaka saklanmalıdır. Ödeme kırılımının iadesi, onayı, onay geri çekmesi ve iyzico ile iletişimde kullanılır. Tercihen itemId ile ilişkili bir şekilde tutulmalıdır. |
| **itemId\(ItemTransactions\)** | String | Üye işyeri tarafından iletilen, sepetteki ürüne ait id. |
| **price\(ItemTransactions\)** | Decimal | Üye işyeri tarafındaki sepetteki ürüne ait tutar. |
| **paidPrice\(ItemTransactions\)** | Decimal | Tahsilat tutarının kırılım bazındaki dağılımı. Üye işyeri tarafından mutlaka saklanmalıdır. |
| **transactionStatus\(ItemTransactions\)** | Integer | Ödeme kırılımının durumu. Ödeme fraud kontrolünde ise 0 değeri döner, bu durumda fraudStatus değeri de 0’dır. Ödeme, fraud kontrolünden sonra reddedilirse -1 döner. Pazaryeri modelinde ürüne onay verilene dek bu değer 1 olarak döner. Pazaryeri modelinde ürüne onay verilmişse bu değer 2 olur. Geçerli değerler: 0, -1, 1, 2 |
| **blockageRate\(ItemTransactions\)** | Decimal | Kırılım bazında üye işyeri blokaj oranı. iyzico – üye işyeri anlaşmasına göre, üye işyerine işlem bazında blokaj uygulayabilir. Bu blokaj üye işyeri fraud riskini önlemek içindir. Blokaj süresi boyunca para iyzico’da tutulur, bu süre sonrasında üye işyerine gönderilir. |
| **blockageRateAmountMerchant\(ItemTransactions\)** | Decimal | Kırılım bazında üye işyeri blokaj tutarının, üye işyerine yansıyan rakamı. Blokaj tutarı mümkün olduğunca üye işyerine yansıtılır. Eğer blokaj tutarı, üye işyeri tutarından daha büyükse bu durumda alt üye işyerine de yansıtılır. |
| **blockageResolvedDate\(ItemTransactions\)** | String | İşlem bazında blokaj çözülme tarihi. yyyy-MM-dd HH:mm:ss formatındadır, örneğin 2015-10-19 14:36:52. |
| **iyziCommissionFee\(ItemTransactions\)** | Decimal | iyzico işlem ücretinin kırılım bazında dağılmış tutarı. |
| **iyziCommissionRateAmount\(ItemTransactions\)** | Decimal | iyzico işlem komisyon tutarının kırılım bazında dağılmış tutarı. |
| **merchantCommissionRate\(ItemTransactions\)** | Decimal | Üye işyerinin uyguladığı vade/komisyon oranının kırılım bazında dağılmış oranı. |
| **merchantCommissionRateAmount\(ItemTransactions\)** | Decimal | Üye işyerinin uyguladığı vade/komisyon tutarının, kırılım bazında dağılmış tutarı. |
| **merchantPayoutAmount\(ItemTransactions\)** | Decimal | Bu kırılım için, iyzico işlem ücreti, komisyon tutarı ve blokajlar düşüldükten sonra üye işyerine gönderilecek tutar. |
| **paidPrice\(ItemTransactions\)\(convertedPayout\)** | Decimal | Tahsilat tutarının kırılım bazındaki dağılımı. Üye işyeri tarafından mutlaka saklanmalıdır. |
| **iyziCommissionFee\(ItemTransactions\)\(convertedPayout\)** | Decimal | iyzico işlem ücretinin kırılım bazında dağılmış tutarı. |
| **iyziCommissionRateAmount\(ItemTransactions\)\(convertedPayout\)** | Decimal | iyzico işlem komisyon tutarının kırılım bazında dağılmış tutarı. |
| **blockageRateAmountMerchant\(ItemTransactions\)\(convertedPayout\)** | Decimal | Kırılım bazında üye işyeri blokaj tutarının, üye işyerine yansıyan rakamı. Blokaj tutarı mümkün olduğunca üye işyerine yansıtılır. Eğer blokaj tutarı, üye işyeri tutarından daha büyükse bu durumda alt üye işyerine de yansıtılır. |
| **merchantPayoutAmount\(ItemTransactions\)\(convertedPayout\)** | Decimal | Bu kırılım için, iyzico işlem ücreti, komisyon tutarı ve blokajlar düşüldükten sonra üye işyerine gönderilecek tutar. |
| **iyziConversationRate\(ItemTransactions\)\(convertedPayout\)** | Decimal | Bu kırılım için, eğer döviz işlemi yapılmışsa çevrim ücreti oranı. |
| **iyziConversationRateAmount\(ItemTransactions\)\(convertedPayout\)** | Decimal | Bu kırılım için, eğer döviz işlemi yapılmışsa çevrim ücreti tutarı. |
| **currency\(ItemTransactions\)\(convertedPayout\)** | String | Ödemenin alındığı para birimi. |
{% endtab %}

{% tab title="Örnek response" %}
```text
{
   "status":"success",
   "locale":"tr",
   "systemTime":1528187049740,
   "conversationId":"123456789",
   "price":1,
   "paidPrice":1,
   "installment":1,
   "paymentId":"10849606",
   "fraudStatus":1,
   "merchantCommissionRate":0,
   "merchantCommissionRateAmount":0,
   "iyziCommissionRateAmount":0.02625,
   "iyziCommissionFee":0.25,
   "cardType":"CREDIT_CARD",
   "cardAssociation":"MASTER_CARD",
   "cardFamily":"Axess",
   "cardToken":"aYoXa2GczmlCXwmhiASXj+j9DCA=",
   "cardUserKey":"puq8I7TG/bH6S8vfmDsux7Yaw0Q=",
   "binNumber":"552608",
   "lastFourDigits":"0006",
   "basketId":"B67832",
   "currency":"TRY",
   "itemTransactions":[
      {
         "itemId":"BI101",
         "paymentTransactionId":"11438592",
         "transactionStatus":1,
         "price":0.3,
         "paidPrice":0.3,
         "merchantCommissionRate":0,
         "merchantCommissionRateAmount":0,
         "iyziCommissionRateAmount":0.007875,
         "iyziCommissionFee":0.075,
         "blockageRate":10,
         "blockageRateAmountMerchant":0.03,
         "blockageRateAmountSubMerchant":0,
         "blockageResolvedDate":"2018-06-12 11:24:09",
         "subMerchantKey":"o+G86/7xLFb9rc6/gVvcM/tGySk=",
         "subMerchantPrice":0.18,
         "subMerchantPayoutRate":60,
         "subMerchantPayoutAmount":0.18,
         "merchantPayoutAmount":0.007125,
         "convertedPayout":{
            "paidPrice":0.3,
            "iyziCommissionRateAmount":0.007875,
            "iyziCommissionFee":0.075,
            "blockageRateAmountMerchant":0.03,
            "blockageRateAmountSubMerchant":0,
            "subMerchantPayoutAmount":0.18,
            "merchantPayoutAmount":0.007125,
            "iyziConversionRate":0,
            "iyziConversionRateAmount":0,
            "currency":"TRY"
         }
      },
      {
         "itemId":"BI102",
         "paymentTransactionId":"11438593",
         "transactionStatus":1,
         "price":0.5,
         "paidPrice":0.5,
         "merchantCommissionRate":0,
         "merchantCommissionRateAmount":0,
         "iyziCommissionRateAmount":0.013125,
         "iyziCommissionFee":0.125,
         "blockageRate":10,
         "blockageRateAmountMerchant":0.05,
         "blockageRateAmountSubMerchant":0,
         "blockageResolvedDate":"2018-06-12 11:24:09",
         "subMerchantKey":"o+G86/7xLFb9rc6/gVvcM/tGySk=",
         "subMerchantPrice":0.18,
         "subMerchantPayoutRate":36,
         "subMerchantPayoutAmount":0.18,
         "merchantPayoutAmount":0.131875,
         "convertedPayout":{
            "paidPrice":0.5,
            "iyziCommissionRateAmount":0.013125,
            "iyziCommissionFee":0.125,
            "blockageRateAmountMerchant":0.05,
            "blockageRateAmountSubMerchant":0,
            "subMerchantPayoutAmount":0.18,
            "merchantPayoutAmount":0.131875,
            "iyziConversionRate":0,
            "iyziConversionRateAmount":0,
            "currency":"TRY"
         }
      },
      {
         "itemId":"BI103",
         "paymentTransactionId":"11438594",
         "transactionStatus":1,
         "price":0.2,
         "paidPrice":0.2,
         "merchantCommissionRate":0,
         "merchantCommissionRateAmount":0,
         "iyziCommissionRateAmount":0.00525,
         "iyziCommissionFee":0.05,
         "blockageRate":10,
         "blockageRateAmountMerchant":0,
         "blockageRateAmountSubMerchant":0.02,
         "blockageResolvedDate":"2018-06-12 11:24:09",
         "subMerchantKey":"o+G86/7xLFb9rc6/gVvcM/tGySk=",
         "subMerchantPrice":0.18,
         "subMerchantPayoutRate":90,
         "subMerchantPayoutAmount":0.12475,
         "merchantPayoutAmount":0,
         "convertedPayout":{
            "paidPrice":0.2,
            "iyziCommissionRateAmount":0.00525,
            "iyziCommissionFee":0.05,
            "blockageRateAmountMerchant":0,
            "blockageRateAmountSubMerchant":0.02,
            "subMerchantPayoutAmount":0.12475,
            "merchantPayoutAmount":0,
            "iyziConversionRate":0,
            "iyziConversionRateAmount":0,
            "currency":"TRY"
         }
      }
   ],
   "authCode":"356247",
   "phase":"AUTH",
   "mdStatus":1,
   "hostReference":"mock00007iyzihostrfn"
}
```
{% endtab %}
{% endtabs %}

### Dönüş parametreleri hakkında notlar

* **status** parametresi işlemin durumu hakkında bilgi verir. **success** ise işlem başarılı bir şekilde yapılmış ve para çekilmiş demektir. **failure** ise işlem başarısız olmuş ve sebebi ile alakalı olarak hata bilgilendirmesi yapılmış demektir.
* **paymentid** ve **paymenttransactionid** değerleri mutlaka saklanmalıdır.

### Örnek Kodlar

* [Php](https://github.com/iyzico/iyzipay-php/blob/master/samples/create_threeds_payment.php#L1)
* [.Net](https://github.com/iyzico/iyzipay-dotnet/blob/master/Iyzipay.Samples/ThreedsSample.cs#L110)
* [Java](https://github.com/iyzico/iyzipay-java/blob/master/src/test/java/com/iyzipay/sample/ThreedsSample.java#L115)
* [Ruby](https://github.com/iyzico/iyzipay-ruby/blob/master/spec/threeds_payment_spec.rb#L192)
* [Python](https://github.com/iyzico/iyzipay-python/blob/master/samples/create_threeds_payment.py#L11)
* [Node.js](https://github.com/iyzico/iyzipay-node/blob/master/samples/IyzipaySamples.js#L947)

