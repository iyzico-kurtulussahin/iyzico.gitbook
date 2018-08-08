---
description: >-
  Wordpress için geliştirilen özelleştirilebilen açık kaynaklı eticaret
  platformu
---

# Woocommerce

{% hint style="info" %}
iyzico woocommerce modülü, yalın woocommerce \(eklentisiz\) kurulumu üzerinde geliştirilip test edilmiştir. Kurulum yaparken mutlaka bu uyarıyı dikkate alınız.
{% endhint %}

Ekibimiz tarafından geliştirilen ve [github.com/iyzico/iyzipay-woocommerce](http://github.com/iyzico/iyzipay-woocommerce) sayfasında bulunan iyzico-woocommerce modülünü, wordpress mağazasından indirmek ve kullanmaya başlamak tamamen ücretsiz.

### **Woocommerce modülünü nasıl entegre edeceğim?**

Aşağıdaki entegrasyon adımlarını takip ederek veya iyzico woocommerce videomuzu izleyerek woocommerce entegrasyonunu gerçekleştirebilirsiniz.

{% embed data="{\"url\":\"https://youtu.be/\_BjALWaLuZU\",\"type\":\"video\",\"title\":\"woocommerce sanalpos eklentisi\",\"icon\":{\"type\":\"icon\",\"url\":\"https://www.youtube.com/yts/img/favicon\_144-vfliLAfaB.png\",\"width\":144,\"height\":144,\"aspectRatio\":1},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://i.ytimg.com/vi/\_BjALWaLuZU/maxresdefault.jpg\",\"width\":1280,\"height\":720,\"aspectRatio\":0.5625},\"embed\":{\"type\":\"player\",\"url\":\"https://www.youtube.com/embed/\_BjALWaLuZU?rel=0&showinfo=0\",\"html\":\"<div style=\\\"left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.2493%;\\\"><iframe src=\\\"https://www.youtube.com/embed/\_BjALWaLuZU?rel=0&amp;showinfo=0\\\" style=\\\"border: 0; top: 0; left: 0; width: 100%; height: 100%; position: absolute;\\\" allowfullscreen scrolling=\\\"no\\\"></iframe></div>\",\"aspectRatio\":1.7778}}" %}

1. Wordpress yönetim panelinize giriş yaptıktan sonra "Eklentiler" bölümünden "Yeni Ekle" butonuna tıkladıktan sonra "Eklentilerde Ara" kısmına iyzico-woocommerce yazın.
2. Karşınıza çıkan iyzico eklentisinde "Yükle" butonuna basın.Böylelikle iyzico eklentisi sisteminize yüklenmiş olacaktır .
3. Wordpress yönetim panelinizde Eklentiler &gt; Yüklü Eklentiler menüsüne ulaşın.
4. iyzico WooCommerce eklentisini bulup aktif hale getirin.
5. Woocommerce &gt;Ayarlar &gt;Ödeme menüsüne gidin ve "iyzico" linkine tıklayın.
6. "iyzico ile ödemeyi etkinleştir" kutucuğunu işaretleyin.
7. Başlık ve tanım için gerekli alanları doldurun. Form Class ayarından ödeme sayfasının "Responsive" veya "PopUp" olarak seçimini yapın. Responsive ve pop-up ödeme formunun sitilini belirtmektedir . Herhangi birini tercih edebilirsiniz . Bu aşamadan sonra sizden iyzico Api ve güvenlik anahtarlarınızı girmeniz istenecektir .
8. iyzico Kontrol Panelinize giriş yapın. Sağ üstteki Ayarlar sekmesinden API Key ve Secret Key değerlerinizin olduğu menüye giriş yapacaksınız. Bu değerleri WooCommerce'teki yönetim sayfanızda ilgili alanlara kopyalayın.
9. Sıralama için ise ödeme seçenekleri arasında hangi sırada görülmesini istiyorsanız o sıra numarasını girin
10. Kaydet butonuna bastıktan sonra iyzico'yu kullanmaya başlayabilirsiniz.

### Demo kurulum

[Buradan](https://www.iyziodeme.com/test/woocommerce) demo woocommerce kurulumuzu inceleyebilirsiniz.

