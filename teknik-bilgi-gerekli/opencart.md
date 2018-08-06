---
description: 'Türkiye''de en çok tercih edilen açık kaynaklı, php tabanlı eticaret platformu'
---

# Opencart

{% hint style="info" %}
iyzico Opencart modülü, yalın opencart \(eklentisiz\) kurulumu üzerinde geliştirilip test edilmiştir. Kurulum yaparken mutlaka bu uyarıyı dikkate alınız.
{% endhint %}

Partnerlerimizden [Kahvedigital](http://kahvedigital.com/) tarafından geliştirilen ve [github.com/kahvedigital](https://github.com/kahvedigital) hesabında bulunan modüllerden, websitenizin altyapısına uygun olan modülü aşağıdaki linkler üzerinden indirebilirsiniz.

* [Opencart 3.x modülü](https://github.com/iyzico/iyzipay-opencart/archive/3.x_1.1.zip)
* [Opencart 2.3 modülü](https://github.com/kahvedigital/iyzico-opencart/archive/2.3.x.zip)
* [Opencart 2.0-2.2 modülü](https://github.com/kahvedigital/iyzico-opencart/archive/2.2.x.zip)
* [Opencart 1.5 modülü](https://github.com/kahvedigital/iyzico-opencart/archive/1.5.6.zip)

### **OpenCart modülünü nasıl entegre edeceğim?**

Aşağıdaki entegrasyon adımlarını takip ederek veya iyzico opencart videomuzu izleyerek opencart entegrasyonunu gerçekleştirebilirsiniz.

{% embed data="{\"url\":\"https://youtu.be/b3P\_SuLMg0c\",\"type\":\"video\",\"title\":\"opencart sanalpos eklentisi\",\"icon\":{\"type\":\"icon\",\"url\":\"https://www.youtube.com/yts/img/favicon\_144-vfliLAfaB.png\",\"width\":144,\"height\":144,\"aspectRatio\":1},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://i.ytimg.com/vi/b3P\_SuLMg0c/maxresdefault.jpg\",\"width\":1280,\"height\":720,\"aspectRatio\":0.5625},\"embed\":{\"type\":\"player\",\"url\":\"https://www.youtube.com/embed/b3P\_SuLMg0c?rel=0&showinfo=0\",\"html\":\"<div style=\\\"left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.2493%;\\\"><iframe src=\\\"https://www.youtube.com/embed/b3P\_SuLMg0c?rel=0&amp;showinfo=0\\\" style=\\\"border: 0; top: 0; left: 0; width: 100%; height: 100%; position: absolute;\\\" allowfullscreen scrolling=\\\"no\\\"></iframe></div>\",\"aspectRatio\":1.7778}}" %}

1. İndirdiğiniz modülün içindeki dosyaları Opencart'ın çalıştığı dizinine yükleyin.
2. Opencart yönetim panelinizdeki Eklentiler menüsünden ödemeleri tıklayın.
3. iyzico eklentisini listeden bulup kurduktan sonra düzenle linkine tıklayın. Bu aşamada sizden iyzico Api ve Güvenlik anahtarlarınızı girmeniz istenecektir.
4. iyzico Kontrol Panelinize giriş yapın. Sağ üstteki Ayarlar sekmesinden API ve Güvenlik anahtarınızı olduğu sayfadan değerleri alıp bu değerleri Opencart'taki yönetim sayfanızda ilgili alanlara kopyalayın. Api ve Güvenlik anahtarınızı kopyalarken baştan ve sondan boşluk kalmamasına dikkat ediniz.
5. "Satın Al" sonrası durum için hazırlanıyor seçeneğini seçin.
6. Form Class ayarından ödeme sayfasının "Responsive" veya "PopUp" olarak seçimini yapın.Responsive ve pop-up ödeme formunun sitilini belirtmektedir. Herhangi birini tercih edebilirsiniz.
7. Modül durumunu "açık" hale getirin.
8. Kaydet butonuna bastıktan sonra iyzico'yu kullanmaya başlayabilirsiniz.

{% hint style="info" %}
Kurulumu bitirdikten sonra mutlaka en az 1 tane gerçek kredi kartınızla cüzi tutarlı bir ödeme yapmanızı öneririz. Bu deneme işlemini iyzico panelinizden anında iptal edebilirsiniz. Başarılı bir test işleminin ardından başvuru durumunuzu “Entegrasyon aşamasından ” “Canlı ” moda güncelliyor olacağız.
{% endhint %}

