# Pazaryeri

{% embed data="{\"url\":\"https://www.youtube.com/watch?v=5tFZjT1HOXI\",\"type\":\"video\",\"title\":\"iyzico Pazaryeri Çözümü\",\"icon\":{\"type\":\"icon\",\"url\":\"https://www.youtube.com/yts/img/favicon\_144-vfliLAfaB.png\",\"width\":144,\"height\":144,\"aspectRatio\":1},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://i.ytimg.com/vi/5tFZjT1HOXI/maxresdefault.jpg\",\"width\":1280,\"height\":720,\"aspectRatio\":0.5625},\"embed\":{\"type\":\"player\",\"url\":\"https://www.youtube.com/embed/5tFZjT1HOXI?rel=0&showinfo=0\",\"html\":\"<div style=\\\"left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.2493%;\\\"><iframe src=\\\"https://www.youtube.com/embed/5tFZjT1HOXI?rel=0&amp;showinfo=0\\\" style=\\\"border: 0; top: 0; left: 0; width: 100%; height: 100%; position: absolute;\\\" allowfullscreen scrolling=\\\"no\\\"></iframe></div>\",\"aspectRatio\":1.7778}}" %}

iyzico pazaryeri çözümünün detaylı açıklaması için aşağıdaki örneği inceleyebilirsiniz.

Pazaryeri altında satış yapan 3 adet Alt Üye İşyeri \(satıcı = submerchant\) olsun. Bu alt üye işyerleri bireysel \(C2C\), şahıs şirketi \(B2C\) veya tüzel kişilik \(B2C\) olabilirler. Bir alıcı 100 TL’lik bir sepet oluşturup 3 farklı satıcıdan, örneğin;

* A satıcısından 30 TL’lik,
* B satıcısından 50 TL’lik,
* C satıcısından 20 TL’lik

3 farklı ürün alabilir. Bilindiği üzere escrow ürün bazındadır; her ürünün satıcısı farklı olabileceği için sepette yer alan her bir ürünün durumu da farklılık gösterebilir. Örneğin A satıcısı ürünü kargolamış, alıcının eline ulaşmış ve ürüne onay verilmiş olabilir. B satıcısının ürünü iade edilmiş/işlem iptal edilmiş; C satıcısının ürünü ise henüz kargo yapılmak üzere bekliyor olabilir.

iyzico, satıcı ve alıcı arasındaki escrow’a müdahil olmaz; ödemenin tahsilatına aracılık eder ve sepetteki ilgili ürün için üye işyerinden para transferine onay verilmesini bekler. Bu süre zarfında alıcının parası bankada korumalı havuz hesapta beklemektedir.

iyzico Pazaryeri çözümü genel olarak para toplama\(collection\) ve dağıtma\(settlement\) süreçlerini kapsamaktadır. Entegrasyonda 3 ana adım bulunmaktadır; adımlar sırasıyla şu şekildedir:

* Alt Üye İşyeri Kaydı
* Ödeme \(API veya Ödeme Formu entegrasyonu tercih edilebilir.\)
* Para Transferi İçin Ürüne Onay Verme

Para transferinin satıcılara \(alt üye işyerlerine\) yapılabilmesi için bu satıcıların iyzico’ya tek seferlik kaydının yapılması gerekir. Bu da onboarding API ile sağlanır; üye işyeri satıcıyı iyzico’ya kaydettiği anda, istek dönüşünde o satıcı için **subMerchanKey** alır.

Ödeme esnasında da sepetteki her bir ürünün satıcısı için ilgili **subMerchantKey** ve bu işlemde satıcıya kaç para gönderilecek ise bu tutar \(**subMerchantPrice**\) iletilmelidir.

{% hint style="info" %}
Ödeme yapılabilen tüm servisler için sepet içerisindeki ürünlere parametreler eklenir. Ödeme, 3D ile ödeme, BKM Express ile ödeme ve Ödeme Formu.
{% endhint %}

| **Parametre ismi** | **Tip** | **Zorunluluk** | **Açıklama** |
| :--- | :--- | :--- | :--- |
| **subMerchantKey** | string | evet | Alt üye işyeri oluşturma sorgusundan dönen değer. |
| **subMerchantPrice** | string | evet | Alt üye işyerine IBAN adresine gönderilmesi istenen tutar. |

{% hint style="info" %}
Sandbox\(test\) hesabı için iyzico'da hesap tipinin pazaryeri hesabı olarak işaretlendiğinden emin olunuz. Sandbox\(test\) üye işyeri numaranız ile entegrasyon@iyzico.com adresine tanımlama talebinizi iletebilirsiniz.
{% endhint %}

Görünüm şu şekilde olacaktır;

* sepet toplam tutarı \(price\),
* indirim vade farkı vs. hesaplanmış POS’tan geçecek yani karttan çekilecek nihai tutarı \(paidPrice\),

sepetteki her bir ürün için;

* ürün fiyatını \(itemPrice\)
* bu ürün için alt üye işyerine gönderilecek tutarı \(subMerchantPrice\)
* alt üye işyeri anahtarını \(subMerchantKey\)

Yukarıdaki örneğe istinaden;

> price = 100 paidPrice=110
>
> basketItem 1 price=30 subMerchantPrice=27 subMerchantKey=G2FCFycIof0paTP6687dOoch9Tc=
>
> basketItem 2 price=50 subMerchantPrice=42 subMerchantKey=D9V/MqIRitUzA4dutL+nCBvnWfs=
>
> basketItem 3 price=20 subMerchantPrice=18 subMerchantKey=D9V/MqIRitUzA4dutL+nCBvnWfs=

Satıcı ve alıcı arasında escrow tamamlanınca da para transferi için ürüne onay verilmelidir. Entegrasyona geçmeden önce mutlaka alıcı ve satıcıların iyzico sözleşmesini kabul etmesi gerekmektedir.

## **Alıcı ve Satıcı Sözleşmeleri**

Pazaryerinizde ödeme akışı iyzico tarafından kontrol edileceği için, alıcılarınızın ve satıcılarınızın, bir kereye mahsus olmak üzere iyzico sözleşmelerini onaylamaları gerekmektedir. Bunun için:

* Alıcılarınızın, [https://www.iyzico.com/pazaryeri-alici-anlasma/ ](https://www.iyzico.com/pazaryeri-alici-anlasma/)sayfasındaki,
* Satıcılarınızın da [https://www.iyzico.com/pazaryeri-satici-anlasma/ ](https://www.iyzico.com/pazaryeri-satici-anlasma/)sayfasındaki iyzico sözleşmesini tek seferlik ve dijital olarak onaylamalarını sağlamalısınız.

Üyelerinize web siteniz üzerinden iyzico hizmet şartlarını iki ayrı şekilde onaylatabilirsiniz:

* Üyelik sırasında
* Ürün listeleme ya da ürün ödeme sayfasında

Her bir üyeniz için bu işlem tek bir defaya mahsustur. iyzico hizmet şartlarını bir önceki listelemesinde ya da ürün ödemesinde kabul etmiş olan üyenizin, sonraki listeleme ya da ödeme aşamalarında sözleşmeyi tekrardan onaylaması gerekmeyecektir.

> > > Alternatif - 1: Üyelik Sırasında Sözleşme Onaylatma Web sitenizdeki üyelik formunun altına "iyzico Platform Kullanım Sözleşmesi"ni Alıcılarınız için, [https://www.iyzico.com/pazaryeri-alici-anlasma/ ](https://www.iyzico.com/pazaryeri-alici-anlasma/)bağlantı adresinden, Satıcılarınız için [https://www.iyzico.com/pazaryeri-satici-anlasma/ ](https://www.iyzico.com/pazaryeri-satici-anlasma/)bağlantı adresinden iframe ile çekebilir ve pazaryerinize üye olmak isteyen kişilerin aynı zamanda iyzico’ya da otomatik olarak kayıt olmalarını sağlayabilirsiniz.
> > >
> > > Alternatif - 2: Ürün Listeleme ya da Ürün Ödeme Sayfasında Kayıt Bu alternatifi kullanarak ayrı ayrı yönlendirmelerle satıcı ve alıcılarınızın iyzico hizmet şartlarını onaylamasını, dolayısıyla birer iyzico üyeliklerinin olmasını sağlayabilirsiniz.

**Satıcılarınız için iyzico kaydı:**

Web siteniz üzerinden ürün satmak isteyen satıcı üyenize, ürün listeleme bölümlerinin herhangi bir aşamasında [https://www.iyzico.com/pazaryeri-satici-anlasma/](https://www.iyzico.com/pazaryeri-satici-anlasma/) bağlantı adresinden iyzico hizmet şartlarını iframe ile çekebilir ve satıcılarınıza onaylatabilirsiniz.

**Alıcılarınız için iyzico kaydı:**

Alıcılarınız da almak istedikleri ürün için ödeme yapacakları sayfada tek sefere mahsus, [https://www.iyzico.com/pazaryeri-alici-anlasma/ ](https://www.iyzico.com/pazaryeri-alici-anlasma/)adresindeki iyzico hizmet şartlarını kabul ederek; ürünü teslim alıp onay verene kadar paralarının güvenli bir şekilde iyzico havuz hesabında bekletileceğini kabul etmelidir.

