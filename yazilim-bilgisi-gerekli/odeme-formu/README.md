---
description: >-
  iyzico'nun ödeme formu teknolojisini 2 basit sorgu ile entegre edebilirsiniz.
  Sizler için 1 adet entegrasyon videosu hazırladık ve popüler olan PHP dilini
  kullandık.
---

# Ödeme Formu

{% embed data="{\"url\":\"https://youtu.be/UzQkrztEMgs\",\"type\":\"video\",\"title\":\"iyzico - Ödeme Formu Entegrasyon Örneği\",\"description\":\"iyzico Ödeme Formu entegrasyonu için hazırladığımız demo çalışmasında iyzipay PHP clientı kullanılarak bir örnek yapılmıştır. iyzico Ödeme Formu entegrasyonu ile hızlı ve kolay bir şekilde ödeme almaya başlayabilirsiniz!\\n\\nSorularınızla ilgili Entegrasyon ekibimize entegrasyon@iyzico.com adresinden ulaşabilirsiniz.\\n\\nhttps://www.iyzico.com/\\nhttps://dev.iyzipay.com/tr\\n\\n\\nBizi takip edin!\\n\\nTwitter: https://twitter.com/iyzico\_com\\nFacebook: https://www.facebook.com/iyzico/\",\"icon\":{\"type\":\"icon\",\"url\":\"https://www.youtube.com/yts/img/favicon\_144-vfliLAfaB.png\",\"width\":144,\"height\":144,\"aspectRatio\":1},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://i.ytimg.com/vi/UzQkrztEMgs/maxresdefault.jpg\",\"width\":1280,\"height\":720,\"aspectRatio\":0.5625},\"embed\":{\"type\":\"player\",\"url\":\"https://www.youtube.com/embed/UzQkrztEMgs?rel=0&showinfo=0\",\"html\":\"<div style=\\\"left: 0; width: 100%; height: 0; position: relative; padding-bottom: 56.2493%;\\\"><iframe src=\\\"https://www.youtube.com/embed/UzQkrztEMgs?rel=0&amp;showinfo=0\\\" style=\\\"border: 0; top: 0; left: 0; width: 100%; height: 100%; position: absolute;\\\" allowfullscreen scrolling=\\\"no\\\"></iframe></div>\",\"aspectRatio\":1.7778},\"caption\":\"iyzico Ödeme Formu Entegrasyon Örneği\"}" %}

{% hint style="info" %}
iyzico ödeme formu ile ödeme almak iki adımdan oluşmaktadır. 

1- Kullanıcıdan alacağınız sipariş bilgileri ile iyzico'dan ödeme formu scriptini çağırmak

2- Yapılan ödemenin sonucunu öğrenme sorgusu
{% endhint %}

### **1 - Ödeme Formu Başlatma**

iyzico'ya yapılan sorgu ile ödeme formu scripti alınarak, iyzico ödeme formu müşteriye gösterilir. Bu servis ile ilgili detaylı bilgiyi aşağıdaki linkten ulaşabileceğiniz ödeme formu başlatma sayfasından edinebilirsiniz.

{% page-ref page="baslat.md" %}

#### Ödeme formu başlatma sorgusu PHP örneği:

{% embed data="{\"url\":\"https://github.com/iyzico/iyzipay-php/blob/master/samples/initialize\_checkout\_form.php\#L1\",\"type\":\"link\",\"title\":\"iyzico/iyzipay-php\",\"description\":\"iyzipay-php - iyzipay api php client\",\"icon\":{\"type\":\"icon\",\"url\":\"https://github.com/fluidicon.png\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://avatars2.githubusercontent.com/u/3815564?s=400&v=4\",\"width\":200,\"height\":200,\"aspectRatio\":1}}" %}

### **2 - Ödeme Formu Sonuç Öğrenme**

Kart sahibi ödeme formu üzerinde ödemesini tamamladıktan sonra, otomatik olarak sonuç sayfasına yönlenir. Bu aşama iyzico tarafından sonuç sayfasına iletilen **"token"** ile ikinci bir sorgu yapılarak ödeme sonucu hakkında ayrıntılı bilgi alınır. Bu servis ile ilgili detaylı bilgiyi aşağıdaki linkten ulaşabileceğiniz ödeme formu sonucu sayfasından edinebilirsiniz.

{% page-ref page="sonuc.md" %}

#### Ödeme formu sonucu sorgusu için Php örneği

{% embed data="{\"url\":\"https://github.com/iyzico/iyzipay-php/blob/master/samples/retrieve\_checkout\_form\_result.php\#L1\",\"type\":\"link\",\"title\":\"iyzico/iyzipay-php\",\"description\":\"iyzipay-php - iyzipay api php client\",\"icon\":{\"type\":\"icon\",\"url\":\"https://github.com/fluidicon.png\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://avatars2.githubusercontent.com/u/3815564?s=400&v=4\",\"width\":200,\"height\":200,\"aspectRatio\":1}}" %}

