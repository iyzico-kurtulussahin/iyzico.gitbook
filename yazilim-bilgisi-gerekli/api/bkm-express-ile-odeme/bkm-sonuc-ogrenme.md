---
description: Bkm Express ile tamamlanan işlmein sonucunu öğrenmek için kullanılır.
---

# Bkm Sonuç Öğrenme

{% embed data="{\"url\":\"https://github.com/iyzico/iyzipay-php/blob/master/samples/retrieve\_bkm\_result.php\#L1\",\"type\":\"link\",\"title\":\"iyzico/iyzipay-php\",\"description\":\"iyzipay-php - iyzipay api php client\",\"icon\":{\"type\":\"icon\",\"url\":\"https://github.com/fluidicon.png\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://avatars2.githubusercontent.com/u/3815564?s=400&v=4\",\"width\":200,\"height\":200,\"aspectRatio\":1},\"caption\":\"Bkm sonuçö öğrenme sorgusu Php örneği\"}" %}

### Parametreler

{% tabs %}
{% tab title="İstek parametreleri" %}
| **Parametre ismi** | **Tip** | **Zorunluluk** | **Açıklama** |
| :--- | :--- | :--- | :--- |
| **locale** | string | hayır | iyzico istek sonucunda dönen metinlerin dilini ayarlamak için kullanılır. Varsayılan değeri tr’dir. |
| **conversationId** | string | hayır | İstek esnasında gönderip, sonuçta alabileceğiniz bir değer, request/response eşleşmesi yapmak için kullanılabilir. |
| **token** | string | evet | Dönüş parametresi olarak yer alan ödeme isteğine özel, iyzico tarafından oluşturulan değer. |
{% endtab %}

{% tab title="Dönüş parametreleri" %}
| **Parametre İsmi** | **Tip** | **Açıklama** |
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
| **installment** | Integer | Ödemenin taksit bilgisi, tek çekim için 1 döner. Geçerli değerler: 1, 2, 3, 6, 9. |
| **paymentStatus** | String | İşlemin sonucunu gösterir. Geçerli değerler SUCCESS, FAILURE, INIT\_THREEDS, CALLBACK\_THREEDS, BKM\_POS\_SELECTED, CALLBACK\_PECCO |
| **basketId** | String | Üye işyeri tarafından gönderilen sepet id’si. |
| **binNumber** | String | Ödeme yapılan kartın ilk 6 hanesi. |
| **cardAssociation** | String | Eğer ödeme yapılan kart yerel bir kart ise, kartın ait olduğu kuruluş. Geçerli değerler: VISA, MASTER\_CARD, AMERICAN\_EXPRESS, TROY |
| **cardFamily** | String | Eğer ödeme yapılan kart yerel bir kart ise, kartın ait olduğu aile. Geçerli değerler: Bonus, Axess, World, Maximum, Paraf, CardFinans, Advantage. |
| **cardType** | String | Eğer ödeme yapılan kart yerel bir kart ise, kartın ait olduğu tipi. Geçerli değerler: CREDIT\_CARD, DEBIT\_CARD, PREPAID\_CARD. |
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
| **blockageRate\(ItemTransactions\)** | Decimal | Kırılım bazında üye işyeri blokaj oranı. iyzico – üye işyeri anlaşmasına göre, üye işyerine işlem bazında blokaj uygulayabilir. Bu blokaj üye işyeri fraud riskini önlemek içindir, blokaj süresi boyunca para iyzico’da tutulur, bu süre sonrası üye işyerine gönderilir. |
| **blockageRateAmountMerchant\(ItemTransactions\)** | Decimal | Kırılım bazında üye işyeri blokaj tutarının, üye işyerine yansıyan rakamı. Blokaj tutarı mümkün olduğunca üye işyerine yansıtılır. Eğer blokaj tutarı, üye işyeri tutarından daha büyükse bu durumda alt üye işyerine de yansıtılır. |
| **blockageResolvedDate\(ItemTransactions\)** | String | İşlem bazında blokaj çözülme tarihi. yyyy-MM-dd HH:mm:ss formatındadır, örneğin 2015-10-19 14:36:52. |
| **iyziCommissionFee\(ItemTransactions\)** | Decimal | iyzzico işlem ücretinin kırılım bazında dağılmış tutarı. |
| **iyziCommissionRateAmount\(ItemTransactions\)** | Decimal | iyzico işlem komisyon tutarının kırılım bazında dağılmış tutarı. |
| **merchantCommissionRate\(ItemTransactions\)** | Decimal | Üye işyerinin uyguladığı vade/komisyon oranının kırılım bazında dağılmış oranı. |
| **merchantCommissionRateAmount\(ItemTransactions\)** | Decimal | Üye işyerinin uyguladığı vade/komisyon tutarıın, kırılım bazında dağılmış tutarı. |
| **merchantPayoutAmount\(ItemTransactions\)** | Decimal | Bu kırılım için, iyzico işlem ücreti, komisyon tutarı ve blokajlar düşüldükten sonra üye işyerine gönderilecek tutar. |
| **paidPrice\(ItemTransactions\)\(convertedPayout\)** | Decimal | Tahsilat tutarının kırılım bazındaki dağılımı. Üye işyeri tarafından mutlaka saklanmalıdır. |
| **iyziCommissionFee\(ItemTransactions\)\(convertedPayout\)** | Decimal | iyzico işlem ücretinin kırılım bazında dağılmış tutarı. |
| **iyziCommissionRateAmount\(ItemTransactions\)\(convertedPayout\)** | Decimal | iyzico işlem komisyon tutarının kırılım bazında dağılmış tutarı |
| **blockageRateAmountMerchant\(ItemTransactions\)\(convertedPayout\)** | Decimal | Kırılım bazında üye işyeri blokaj tutarının, üye işyerine yansıyan rakamı. Blokaj tutarı mümkün olduğunca üye işyerine yansıtılır. Eğer blokaj tutarı, üye işyeri tutarından daha büyükse bu durumda alt üye işyerine de yansıtılır. |
| **merchantPayoutAmount\(ItemTransactions\)\(convertedPayout\)** | Decimal | Bu kırılım için, iyzico işlem ücreti, komisyon tutarı ve blokajlar düşüldükten sonra üye işyerine gönderilecek tutar. |
| **iyziConversationRate\(ItemTransactions\)\(convertedPayout\)** | Decimal | Bu kırılım için, iyzico işlem ücreti, komisyon tutarı ve blokajlar düşüldükten sonra üye işyerine gönderilecek tutar. |
| **iyziConversationRateAmount\(ItemTransactions\)\(convertedPayout\)** | Decimal | Bu kırılım için, iyzico işlem ücreti, komisyon tutarı ve blokajlar düşüldükten sonra üye işyerine gönderilecek tutar. |
| **currency\(ItemTransactions\)\(convertedPayout\)** | String | Ödemenin alındığı para birimi. |
| **token** | String | Ödeme isteğine özel, iyzico tarafından oluşturulan değer. |
{% endtab %}

{% tab title="Örnek response" %}
```text
{
   "status":"success",
   "locale":"tr",
   "systemTime":1528119414851,
   "conversationId":"123456789",
   "price":0.3,
   "paidPrice":0.3,
   "installment":2,
   "paymentId":"10848450",
   "fraudStatus":1,
   "merchantCommissionRate":0,
   "merchantCommissionRateAmount":0,
   "iyziCommissionRateAmount":0.01134,
   "iyziCommissionFee":0.25,
   "cardType":"CREDIT_CARD",
   "cardAssociation":"VISA",
   "cardFamily":"Maximum",
   "binNumber":"469884",
   "lastFourDigits":"0000",
   "basketId":"B67832",
   "currency":"TRY",
   "itemTransactions":[
      {
         "itemId":"BI101",
         "paymentTransactionId":"11437271",
         "transactionStatus":2,
         "price":0.3,
         "paidPrice":0.3,
         "merchantCommissionRate":0,
         "merchantCommissionRateAmount":0,
         "iyziCommissionRateAmount":0.01134,
         "iyziCommissionFee":0.25,
         "blockageRate":10,
         "blockageRateAmountMerchant":0.03,
         "blockageRateAmountSubMerchant":0,
         "blockageResolvedDate":"2018-06-11 16:36:27",
         "subMerchantPrice":0,
         "subMerchantPayoutRate":0,
         "subMerchantPayoutAmount":0,
         "merchantPayoutAmount":0.00866,
         "convertedPayout":{
            "paidPrice":0.3,
            "iyziCommissionRateAmount":0.01134,
            "iyziCommissionFee":0.25,
            "blockageRateAmountMerchant":0.03,
            "blockageRateAmountSubMerchant":0,
            "subMerchantPayoutAmount":0,
            "merchantPayoutAmount":0.00866,
            "iyziConversionRate":0,
            "iyziConversionRateAmount":0,
            "currency":"TRY"
         }
      }
   ],
   "authCode":"authCode",
   "phase":"AUTH",
   "hostReference":"hostRefNum",
   "token":"mockToken_1528119159167",
   "callbackUrl":"https://www.merchant.com/callback",
   "paymentStatus":"SUCCESS"
}
```
{% endtab %}
{% endtabs %}

