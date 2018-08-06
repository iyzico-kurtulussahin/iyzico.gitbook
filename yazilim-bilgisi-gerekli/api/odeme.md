# Ödeme

{% embed data="{\"url\":\"https://github.com/iyzico/iyzipay-php/blob/master/samples/create\_payment.php\#L1\",\"type\":\"link\",\"title\":\"iyzico/iyzipay-php\",\"description\":\"iyzipay-php - iyzipay api php client\",\"icon\":{\"type\":\"icon\",\"url\":\"https://github.com/fluidicon.png\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://avatars2.githubusercontent.com/u/3815564?s=400&v=4\",\"width\":200,\"height\":200,\"aspectRatio\":1},\"caption\":\"Ödeme sorgusu Php örneği\"}" %}

Ödeme sorgusu, müşterinin kredi kartından para çekme işlemini yapar. İlgili servis kullanıldığında iyzico işlemin başarılı olup olmadığı ile alakalı olarak yanıtı anında döner.

* Üzerinde **TROY**, **MASTERCARD**, **VISA**, **AMEX** logolu kartlardan işlem yapmaya olanak verir.
* Üzerinde **BONUS**, **WORLD**, **MAXIMUM**, **AXESS**, **CARDFINANS**, **PARAF**, **ADVANTAGE** taksit programlarına dahil kartlar için **2**, **3**, **6**, **9**, **12** taksit seçenekleri bu servis ile kullanılabilir.
* Başarılı işlemler **yeşil**, başarısız işlemler ise **kırmızı** renkte panel üzerinde görüntülenebilir.
* Üye işyeri tarafında sipariş numarası olarak **conversationId** ve **basketId** parametreleri kullanılabilir.

### Parametreler

{% tabs %}
{% tab title="İstek Parametreleri" %}
| **Parametre İsmi** | **Tip** | **Zorunlu** | **Açıklama** |
| :--- | :--- | :--- | :--- |
| **locale** | String | Hayır | iyzico istek sonucunda dönen metinlerin dilini ayarlamak için kullanılır. Varsayılan değeri **tr**’dir. **en** olarak kullanılabilir. |
| **conversationId** | String | Hayır | İstek esnasında gönderip, sonuçta alabileceğiniz bir değer, request/response eşleşmesi yapmak için kullanılabilir. En yaygın kullanış biçimi üye iş yerinin sipariş numarasıdır. |
| **price** | Decimal | Evet | Ödeme sepet tutarı. Kırılım \(sepetin içerisindeki ürünler\) tutarlar toplamı sepet tutarına eşit olmalı. |
| **paidPrice** | Decimal | Evet | İndirim vade farkı vs. hesaplanmış POS’tan geçecek nihai tutar. Price değerinden küçük, büyük veya eşit olabilir. |
| **currency** | String | Evet | Ödemenin alınacağı para birimi default TRY olarak belirlenmiştir. Diğer değerler ise USD, EUR, GBP olmak üzere, farklı para birimleri ile alışverişin hesabınıza tanımlandığından emin olunuz. |
| **installment** | Integer | Evet | Taksit bilgisi, tek çekim için 1 gönderilmelidir. Geçerli değerler: **1**, **2**, **3**, **6**, **9**, **12** |
| **basketId** | String | Hayır | Üye işyeri tarafından ilgili ödemenin sepetini tanımlamak için kullanılan id'dir. Sipariş numarası ya da anlamlı bir değer olabilir. |
| **paymentChannel** | String | Hayır | Ödeme kanalı. Geçerli değerler enum içinde sunulmaktadır: WEB, MOBILE, MOBILE\_WEB, MOBILE\_IOS, MOBILE\_ANDROID, MOBILE\_WINDOWS, MOBILE\_TABLET, MOBILE\_PHONE |
| **paymentGroup** | String | Hayır | Ödeme grubu, varsayılan **PRODUCT**. Geçerli değerler enum içinde sunulmaktadır: **PRODUCT**, **LISTING**, **SUBSCRIPTION**, **OTHER**. |
| **cardNumber** | String | Evet | Ödemenin alınacağı kart numarası. Eğer saklı kart ile ödeme yapılmıyorsa zorunludur. |
| **expireYear** | String | Evet | Ödemenin alınacağı kartın son kullanma tarihi yılı. Eğer saklı kart ile ödeme yapılmıyorsa zorunludur. |
| **expireMonth** | String | Evet | Ödemenin alınacağı kartın son kullanma tarihi ayı. Eğer saklı kart ile ödeme yapılmıyorsa zorunludur. |
| **cvc** | String | Evet | Ödemenin alınacağı kartın güvenlik kodu. Eğer saklı kart ile ödeme yapılmıyorsa zorunludur. Saklı kartla ödeme yapılırken gönderilirse aynen bankaya iletilir. |
| **cardHolderName** | String | Evet | Ödemenin alınacağı kart sahibinin adı soyadı. Eğer saklı kart ile ödeme yapılmıyorsa zorunludur. |
| **registerCard** | Integer | Hayır | Ödeme esnasında kartın kaydedilip kaydedilmeyeceğini belirleyen parametre. Varsayılan değeri 0 olup, geçerli değerler 0 ve 1’dir. |
| **id\(Buyer\)** | String | Evet | Üye işyeri tarafındaki alıcıya ait id. |
| **name\(Buyer\)** | String | Evet | Üye işyeri tarafındaki alıcıya ait ad. |
| **surname\(Buyer\)** | String | Evet | Üye işyeri tarafındaki alıcıya ait soyad. |
| **identityNumber\(Buyer\)** | String | Evet | Üye işyeri tarafındaki alıcıya ait kimlik \(TCKN\) numarası. |
| **city\(Buyer\)** | String | Evet | Üye işyeri tarafındaki alıcıya ait şehir bilgisi. |
| **country\(Buyer\)** | String | Evet | Üye işyeri tarafındaki alıcıya ait ülke bilgisi. |
| **email\(Buyer\)** | String | Evet | Üye işyeri tarafındaki alıcıya ait e-posta bilgisi. E-posta adresi alıcıya ait geçerli ve erişilebilir bir adres olmalıdır. |
| **gsmNumber\(Buyer\)** | String | Hayır | Üye işyeri tarafındaki alıcıya ait GSM numarası. |
| **ip\(Buyer\)** | String | Evet | Üye işyeri tarafındaki alıcıya ait IP adresi. |
| **registrationAddress\(Buyer\)** | String | Evet | Üye işyeri tarafındaki alıcıya ait kayıt adresi. |
| **zipCode\(Buyer\)** | String | Hayır | Üye işyeri tarafındaki alıcıya ait posta kodu. |
| **registrationDate\(Buyer\)** | String | Hayır | Üye işyeri tarafındaki alıcıya ait kayıt tarihi. Tarih formatı 2015-09-17 23:45:06 şeklinde olmalıdır. |
| **lastLoginDate\(Buyer\)** | String | Hayır | Üye işyeri tarafındaki alıcıya ait son giriş tarihi. Tarih formatı 2015-09-17 23:45:06 şeklinde olmalıdır. |
| **contactName\(BillingAddress\)** | String | Evet | Üye işyeri tarafındaki fatura adresi, ad soyad bilgisi. |
| **city\(BillingAddress\)** | String | Evet | Üye işyeri tarafındaki fatura adresi şehir bilgisi. |
| **country\(BillingAddress\)** | String | Evet | Üye işyeri tarafındaki fatura adresi ülke bilgisi. |
| **address\(BillingAddress\)** | String | Evet | Üye işyeri tarafındaki fatura adresi. |
| **zipCode\(BillingAddress\)** | String | Hayır | Üye işyeri tarafındaki fatura adresi posta kodu. |
| **contactName\(ShippingAddress\)** | String | Evet | Üye işyeri tarafındaki teslimat adresi, ad soyad bilgisi. Sepetteki ürünlerden en az 1 tanesi fiziksel ürün \(itemType=PHYSICAL\) ise zorunludur. |
| **city\(ShippingAddress\)** | String | Evet | Üye işyeri tarafındaki teslimat adresi şehir bilgisi. Sepetteki ürünlerden en az 1 tanesi fiziksel ürün \(itemType=PHYSICAL\) ise zorunludur. |
| **country\(ShippingAddress\)** | String | Evet | Üye işyeri tarafındaki teslimat adresi ülke bilgisi. Sepetteki ürünlerden en az 1 tanesi fiziksel ürün \(itemType=PHYSICAL\) ise zorunludur. |
| **address\(ShippingAddress\)** | String | Evet | Üye işyeri tarafındaki teslimat adresi. Sepetteki ürünlerden en az 1 tanesi fiziksel ürün \(itemType=PHYSICAL\) ise zorunludur. |
| **zipCode\(ShippingAddress\)** | String | Hayır | Üye işyeri tarafındaki teslimat adresi posta kodu. |
| **id\(BasketItems\)** | String | Evet | Üye işyeri tarafındaki sepetteki ürüne ait id. |
| **itemType\(BasketItems\)** | String | Evet | Üye işyeri tarafındaki sepetteki ürüne ait tip. Geçerli enum değerler: PHYSICAL ve VIRTUAL. |
| **name\(BasketItems\)** | String | Evet | Üye işyeri tarafındaki sepetteki ürüne ait isim. |
| **category1\(BasketItems\)** | String | Evet | Üye işyeri tarafındaki sepetteki ürüne ait kategori 1. |
| **category2\(BasketItems\)** | String | Hayır | Üye işyeri tarafındaki sepetteki ürüne ait kategori 2. |
| **price\(BasketItems\)** | Decimal | Evet | Üye işyeri tarafındaki sepetteki ürüne ait tutar. 0 ve 0’dan küçük olamaz; tutarlar toplamı sepet tutarına \(price\) eşit olmalıdır. |
{% endtab %}

{% tab title="Dönüş Parametreleri" %}
| **Parametre İsmi** | **Tip** | **Açıklama** |
| :--- | :--- | :--- |
| **status** | String | Yapılan isteğin sonucunu bildirir. İşlem başarılı ise **success**, hatalı ise **failure** döner. |
| **errorCode** | String | İşlem hatalıysa, bu hataya dair belirtilen koddur. |
| **errorMessage** | String | İşlem hatalıysa, bu hataya dair belirtilen mesajdır, locale parametresine göre dil desteği sunar. |
| **errorGroup** | String | İşlem hatalıysa, bu hataya dair belirtilen gruptur. |
| **locale** | String | İstekte belirtilen locale değeri geri dönülür, varsayılan değeri tr’dir. |
| **systemTime** | Long | Dönen sonucun o anki unix timestamp değeridir. |
| **conversationId** | String | İstek esnasında gönderilmişse, sonuçta aynen geri iletilir. |
| **paymentId** | String | Ödemeye ait id, üye işyeri tarafından mutlaka saklanmalıdır. Ödemenin iptali ve iyzico ile iletişimde kullanılır. |
| **price** | Decimal | Ödeme sepet tutarı. Kırılım tutarlar toplamı sepet tutarına eşit olmalı. |
| **paidPrice** | Decimal | İndirim vade farkı vs. hesaplanmış POS’tan geçen, tahsil edilen, nihai tutar. |
| **currency** | String | Ödemenin alındığı para birimi. |
| **installment** | Integer | Ödemenin taksit bilgisi, tek çekim için 1 döner. Geçerli değerler: 1, 2, 3, 6, 9. |
| **basketId** | String | Üye işyeri tarafından gönderilen sepet id’si. |
| **binNumber** | String | Ödeme yapılan kartın ilk 6 hanesi. |
| **cardAssociation** | String | Eğer ödeme yapılan kart yerel bir kart ise, kartın ait olduğu kuruluş. Geçerli değerler: VISA, MASTER\_CARD, AMERICAN\_EXPRESS, TROY |
| **cardFamily** | String | Eğer ödeme yapılan kart yerel bir kart ise, kartın ait olduğu aile. Geçerli değerler: Bonus, Axess, World, Maximum, Paraf, CardFinans, Advantage |
| **cardType** | String | Eğer ödeme yapılan kart yerel bir kart ise, kartın ait olduğu tipi. Geçerli değerler: CREDIT\_CARD, DEBIT\_CARD, PREPAID\_CARD. |
| **fraudStatus** | Integer | Ödeme işleminin fraud filtrelerine göre durumu. Eğer ödemenin fraud risk skoru düşük ise ödemeye anında onay verilir, bu durumda 1 değeri döner. Eğer fraud risk skoru yüksek ise ödeme işlemi reddedilir ve -1 döner. Eğer ödeme işlemi daha sonradan incelenip karar verilecekse 0 döner. Geçerli değerler: 0, -1 ve 1. Üye işyeri sadece 1 olan işlemlerde ürünü kargoya vermelidir, 0 olan işlemler için bilgilendirme beklemelidir. |
| **iyziCommissionFee** | Decimal | Ödemeye ait iyzico işlem ücreti . |
| **iyziCommissionRateAmount** | Decimal | Ödemeye ait iyzico işlem komisyon tutarı. |
| **merchantCommissionRate** | Decimal | Üye işyerinin uyguladığı vade/komisyon oranı. Örneğin price=100, paidPrice=110 ise üye işyeri vade/komisyon oranı %10’dur. Bilgi amaçlıdır. |
| **merchantCommissionRateAmount** | Decimal | Üye işyerinin uyguladığı vade/komisyon tutarı. Örneğin price=100, paidPrice=110 ise üye işyeri vade/komisyon tutarı 10’dur. Bilgi amaçlıdır. |
| **paymentTransactionId \(ItemTransactions\)** | String | Ödeme kırılımına ait id, üye işyeri tarafından mutlaka saklanmalıdır. Ödeme kırılımının iadesi, onayı, onay geri çekmesi ve iyzico ile iletişimde kullanılır. Tercihen itemId ile ilişkili bir şekilde tutulmalıdır. |
| **itemId\(ItemTransactions\)** | String | Üye işyeri tarafından iletilen, sepetteki ürüne ait id. |
| **price\(ItemTransactions\)** | Decimal | Üye işyeri tarafındaki sepetteki ürüne ait tutar. |
| **paidPrice\(ItemTransactions\)** | Decimal | Tahsilat tutarının kırılım bazındaki dağılımı. Üye işyeri tarafından mutlaka saklanmalıdır. |
| **transactionStatus \(ItemTransactions\)** | Integer | Ödeme kırılımının durumu. Ödeme fraud kontrolünde ise 0 değeri döner, bu durumda fraudStatus değeri de 0’dır. Ödeme, fraud kontrolünden sonra reddedilirse -1 döner. Pazaryeri modelinde ürüne onay verilene dek bu değer 1 olarak döner. Pazaryeri modelinde ürüne onay verilmişse bu değer 2 olur. Geçerli değerler: 0, -1, 1, 2. |
| **blockageRate\(ItemTransactions\)** | Decimal | Kırılım bazında üye işyeri blokaj oranı. iyzico – üye işyeri anlaşmasına göre, üye işyerine işlem bazında blokaj uygulayabilir. Bu blokaj üye işyeri fraud riskini önlemek içindir. Blokaj süresi boyunca para iyzico’da tutulur, bu süre sonrası üye işyerine gönderilir. |
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
   "locale":"TR",
   "systemTime":1528282342393,
   "conversationId":"123456789",
   "price":1,
   "paidPrice":1.2,
   "installment":1,
   "paymentId":"10851936",
   "fraudStatus":1,
   "merchantCommissionRate":20,
   "merchantCommissionRateAmount":0.2,
   "iyziCommissionRateAmount":0.0315,
   "iyziCommissionFee":0.25,
   "cardType":"CREDIT_CARD",
   "cardAssociation":"MASTER_CARD",
   "cardFamily":"Paraf",
   "binNumber":"552879",
   "lastFourDigits":"0008",
   "basketId":"B67832",
   "currency":"TRY",
   "itemTransactions":[
      {
         "itemId":"BI101",
         "paymentTransactionId":"11441121",
         "transactionStatus":2,
         "price":0.3,
         "paidPrice":0.36,
         "merchantCommissionRate":20,
         "merchantCommissionRateAmount":0.06,
         "iyziCommissionRateAmount":0.00945,
         "iyziCommissionFee":0.075,
         "blockageRate":10,
         "blockageRateAmountMerchant":0.036,
         "blockageRateAmountSubMerchant":0,
         "blockageResolvedDate":"2018-06-13 13:52:22",
         "subMerchantPrice":0,
         "subMerchantPayoutRate":0,
         "subMerchantPayoutAmount":0,
         "merchantPayoutAmount":0.23955,
         "convertedPayout":{
            "paidPrice":0.36,
            "iyziCommissionRateAmount":0.00945,
            "iyziCommissionFee":0.075,
            "blockageRateAmountMerchant":0.036,
            "blockageRateAmountSubMerchant":0,
            "subMerchantPayoutAmount":0,
            "merchantPayoutAmount":0.23955,
            "iyziConversionRate":0,
            "iyziConversionRateAmount":0,
            "currency":"TRY"
         }
      },
      {
         "itemId":"BI102",
         "paymentTransactionId":"11441122",
         "transactionStatus":2,
         "price":0.5,
         "paidPrice":0.6,
         "merchantCommissionRate":20,
         "merchantCommissionRateAmount":0.1,
         "iyziCommissionRateAmount":0.01575,
         "iyziCommissionFee":0.125,
         "blockageRate":10,
         "blockageRateAmountMerchant":0.06,
         "blockageRateAmountSubMerchant":0,
         "blockageResolvedDate":"2018-06-13 13:52:22",
         "subMerchantPrice":0,
         "subMerchantPayoutRate":0,
         "subMerchantPayoutAmount":0,
         "merchantPayoutAmount":0.39925,
         "convertedPayout":{
            "paidPrice":0.6,
            "iyziCommissionRateAmount":0.01575,
            "iyziCommissionFee":0.125,
            "blockageRateAmountMerchant":0.06,
            "blockageRateAmountSubMerchant":0,
            "subMerchantPayoutAmount":0,
            "merchantPayoutAmount":0.39925,
            "iyziConversionRate":0,
            "iyziConversionRateAmount":0,
            "currency":"TRY"
         }
      },
      {
         "itemId":"BI103",
         "paymentTransactionId":"11441123",
         "transactionStatus":2,
         "price":0.2,
         "paidPrice":0.24,
         "merchantCommissionRate":20,
         "merchantCommissionRateAmount":0.04,
         "iyziCommissionRateAmount":0.0063,
         "iyziCommissionFee":0.05,
         "blockageRate":10,
         "blockageRateAmountMerchant":0.024,
         "blockageRateAmountSubMerchant":0,
         "blockageResolvedDate":"2018-06-13 13:52:22",
         "subMerchantPrice":0,
         "subMerchantPayoutRate":0,
         "subMerchantPayoutAmount":0,
         "merchantPayoutAmount":0.1597,
         "convertedPayout":{
            "paidPrice":0.24,
            "iyziCommissionRateAmount":0.0063,
            "iyziCommissionFee":0.05,
            "blockageRateAmountMerchant":0.024,
            "blockageRateAmountSubMerchant":0,
            "subMerchantPayoutAmount":0,
            "merchantPayoutAmount":0.1597,
            "iyziConversionRate":0,
            "iyziConversionRateAmount":0,
            "currency":"TRY"
         }
      }
   ],
   "authCode":"235467",
   "phase":"AUTH",
   "hostReference":"mock00001iyzihostrfn"
}
```
{% endtab %}
{% endtabs %}

### Dikkat edilmesi gereken noktalar

* **status** parametresi işlemin durumu hakkında bilgi verir. **success** işlem başarılı bir şekilde yapılmış ve para çekilmiş demektir. **failure** ise işlem başarısız olmuş ve sebebi ile alakalı olarak hata bilgilendirmesi yapılmış anlamına gelmektedir.
* **paymentStatus** bu servis için null olarak gelmektedir.
* **paymentid** ve **paymenttransactionid** değerleri mutlaka saklanmalıdır.
* Eğer işlem failure statüsü ile sonlanmış ise **errorCode**, **errorMessage**, **errorGroup** parametreleri değerler ile dönecektir.

### Github - **Örnek Kodlar**

* [Php](https://github.com/iyzico/iyzipay-php/blob/master/samples/create_payment.php#L1)
* [.Net](https://github.com/iyzico/iyzipay-dotnet/blob/master/Iyzipay.Samples/PaymentSample.cs#L11)
* [Java](https://github.com/iyzico/iyzipay-java/blob/master/src/test/java/com/iyzipay/sample/PaymentSample.java#L17)
* [Ruby](https://github.com/iyzico/iyzipay-ruby/blob/master/spec/payment_spec.rb#L13)
* [Python](https://github.com/iyzico/iyzipay-python/blob/master/samples/create_payment.py#L11)
* [Node.js](https://github.com/iyzico/iyzipay-node/blob/master/samples/IyzipaySamples.js#L334)

