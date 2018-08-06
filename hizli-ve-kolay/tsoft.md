---
description: >-
  T-Soft E-Ticaret Sistemleri - Tel: 0212 612 44 55 - Destek :
  destek.tsoft.com.tr
---

# Tsoft

iyzico entegrasyon sürecini sizler için daha anlaşılabilir ve kolay kılmak için bir entegrasyon rehberi hazırladık.

Rehberde yanıt bulamadığınız ve de anlaşılır gelmeyen konularla ilgili bize entegrasyon@iyzico.com adresi üzerinden ulaşabilirsiniz, sizlere yardımcı olmaktan mutluluk duyarız.

1. **Api anahtaraları :** Siteniz üzerinde iyzico ile bağlantı kurmanız için gerekli olan anahtarlardır.
2. **Sitenizin altyapısı :** Sitenizin altyapısına uygun modülümüzü indirerek entegrasyonu gerçekleştirmelisiniz.
3. **Entegrasyon testleri :** Ödeme sisteminin sitenizde sağlıklı şekilde çalıştığından emin olmak için gerekli olan en temel testlerdir.

### **Api Anahtarı ve Güvenlik Anahtarı** {#api-anahtari-ve-guevenlik-anahtari}

"API Anahtarı" ve "Güvenlik Anahtarı" bilgilerine iyzico panelinize [https://merchant.iyzipay.com/login](https://merchant.iyzipay.com/login) adresinden girerek, Ayarlar menüsünden ulaşabilirsiniz.

Api anahtarlarınız iyzico ile bağlantı kurmanızı sağlayan temel değerlerdir.

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-LH1lc6K6sXEqXUGHpw6%2F-LHDAny9AyuEoODhXFz7%2F-LHDCnkaw8UukYwI6Do3%2FScreen_Shot_2018-07-11_at_10_13_26.png?alt=media&token=267a0eaf-679b-41cd-ba33-3e07bd0f2c7d)

### **Site Altyapısı** {#site-altyapisi}

“Api Anahtarı" ve "Güvenlik Anahtarı" bilgilerinizi sitenizin yönetici panelinde, iyzico ayarları kısmında, ilgili bölüme giriniz. Bu konuda altyapı sağlayıcınızdan destek alabilir, aşağıdaki adımları takip ederek entegrasyonu gerçekleştirebilirsiniz.

**Adım 1 :**

T-soft panelinizde **Siparişler-&gt;Ödeme Seçenekleri** kısmına tıklayarak iyzico ayarlarının olduğu kısma ulaşabilirsiniz.

![](../.gitbook/assets/picture1-4.png)

![](file:////Users/kurtulus.sahin/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_image003.png)

**Adım 2 :**

Ödeme Seçenkleri sayfasında “iyzico” seçeneğinin yanındaki düzenle butonuna bastığınızda, iyzico api anahtarlarınızı girmeniz için gerekli alan açılır. \(Eğer iyzico seçeneği bulunmuyor ise T-soft destek ekibi ile iletişime geçerek, iyzico seçeneğinin sitenizde aktif olmasını sağlayabilirsiniz\)

![](../.gitbook/assets/picture1-6.png)

**Adım 3 :**

Mode kısmını “LIVE” seçip api anahtarlarınızı girerek “kaydet” butonuna basınız.

![](../.gitbook/assets/picture1-7.png)

**Adım 4 :**![](file:////Users/kurtulus.sahin/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_image008.png)

iyzico yazısının üzerine çift tıklayarak dilerseniz, ödeme sayfanızda görünecek ismi “Kredi Kartı” olarak değiştirebilir, ek olarak ödeme sayfanızdaki sıralamasını da “sıra no” kısmından değiştirebilirsiniz.

![](../.gitbook/assets/picture1-8.png)

{% hint style="success" %}
Artık siteniz ödeme almak için hazır.
{% endhint %}

### **Entegrasyon Testleri**

-Ödeme \(başarılı ve başarısız\)

-3ds ödeme

-3ds ödemede, 3ds ekranında vazgeç butonuna basmak

-Taksitli ödeme \(sepette taksite izin olmayan bir ürün var ise taksit seçeneklerinin görüntülenmemesi\)

-Sepette birden fazla ürün ile ödeme

Yaptığınız test işlemlerini iyzico kontrol panelinizden kontrol etmeyi unutmayın.

Tüm ödeme işlemlerinizi iyzico panelinizden anında iptal edebilirsiniz.

