# Ticimax

iyzico entegrasyon sürecini sizler için daha anlaşılabilir ve kolay kılmak için bir entegrasyon rehberi hazırladık.

Rehberde yanıt bulamadığınız ve de anlaşılır gelmeyen konularla ilgili bize  entegrasyon@iyzico.com adresi üzerinden ulaşabilirsiniz, sizlere yardımcı olmaktan mutluluk duyarız.

1. **Api anahtaraları :** Siteniz üzerinde iyzico ile bağlantı kurmanız için gerekli olan anahtarlardır.
2. **Sitenizin altyapısı :** Sitenizin altyapısına uygun modülümüzü indirerek entegrasyonu gerçekleştirmelisiniz.
3. **Entegrasyon testleri :** Ödeme sisteminin sitenizde sağlıklı şekilde çalıştığından emin olmak için gerekli olan en temel testlerdir.

### **Api Anahtarı ve Güvenlik Anahtarı**  {#api-anahtari-ve-guevenlik-anahtari}

"API Anahtarı" ve "Güvenlik Anahtarı" bilgilerine iyzico panelinize [https://merchant.iyzipay.com/login](https://merchant.iyzipay.com/login) adresinden girerek,  Ayarlar menüsünden ulaşabilirsiniz.

Api anahtarlarınız iyzico ile bağlantı kurmanızı sağlayan temel değerlerdir.

![](../.gitbook/assets/screen_shot_2018-07-11_at_10_13_26%20%282%29.png)

### **Site Altyapısı**

“Api Anahtarı" ve "Güvenlik Anahtarı" bilgilerinizi sitenizin yönetici panelinde, iyzico ayarları kısmında,  ilgili bölüme giriniz. Bu konuda altyapı sağlayıcınızdan destek alabilir, aşağıdaki adımları takip ederek entegrasyonu gerçekleştirebilirsiniz.. 

Ek olarak Ticimax tarafından hazırlanmış [http://destekalani.com/Icerik/iyzico-kurulumu-157](http://destekalani.com/Icerik/iyzico-kurulumu-157) adresindeki dökümanı inceleyebilirsiniz.

**Adım 1.**

Ticimax panelinizde, **Ayarlar-&gt;Genel Ayarlar** kısmına tıklayarak iyzico ayarlarının olduğu kısma ulaşabilirsiniz.

![](../.gitbook/assets/picture1.png)

**Adım 2.**

Genel Ayarlar bölümünden **Ödeme Ayarları**’na tıklayın.

**iyzipay Ödeme** seçeneğini aktif edin.

**iyziPay Api Key** kısmına api anahtarınızı girin.

**Iyzipay Secret Key** kısmına güvenlik anahtarınızı girin.

![](../.gitbook/assets/picture1-3.png)

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

