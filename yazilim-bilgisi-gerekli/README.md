---
description: >-
  iyzico'nun ödeme formunu veya API'sini entegre etmek için gerekli kodlara
  buradan ulaşabilirsiniz.
---

# Yazılım bilgisi gerekli

### **İstemci\(client\) seçimi**

{% hint style="info" %}
Kütüphanelerimize ve kod örneklerimize [github iyzico hesabı](https://github.com/iyzico) üzerinden ulaşabilirsiniz.

Ek olarak Composer, Nuget, Maven, pip, gem, npm üzerinden iyzipay yazıp projelerinize dahil edebilirsiniz
{% endhint %}

{% embed data="{\"url\":\"https://github.com/iyzico\",\"type\":\"link\",\"title\":\"iyzico\",\"description\":\"Easiest and Fastest Way of Accepting Payments\",\"icon\":{\"type\":\"icon\",\"url\":\"https://github.com/fluidicon.png\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://avatars1.githubusercontent.com/u/3815564?s=280&v=4\",\"width\":200,\"height\":200,\"aspectRatio\":1}}" %}

### Sandbox \(Test\) Ortamı

### İyzico ödeme formu entegrasyonu

{% page-ref page="odeme-formu/" %}

### **Entegrasyon sürecinde dikkat edilecek noktalar**

* Canlı ortamda iyzico API'ına gönderilen parametrelere müşteriden alınan bilgiler set edilmelidir. Müşteriniden alınmayan "dummy" değerler sorgu parametrelerine set edilmemelidir.
* Ödeme işlemi sonucunda iyzico tarafından dönen cevaptaki değerler \(price, paidPrice, basketId, conversationId\) ile sizin sisteminize kaydettiğiniz değerleri karşılaştırarak bir farklılık var ise genel bir hata mesajı gösterebilirsiniz. Bu tür durumlarda iyzico entegrasyon ekibi ile iletişime geçmeyi unutmayınız. Müşteri tarafından ödenen tutar iyzico tarafından dönen cevaptaki paidPrice parametresindeki değere eşittir.

### **Canlı ortama geçiş**

* Geliştirmeler tamamlandıktan sonra ödeme adımlarınızı, test kartlarınız ile tüm durumlar için test edin.
* iyzico servislerinden dönen ve olabilecek tüm hataları karşılayacak şekilde kodunuzu düzenleyin.
* Sonuç sayfanızın iyzico'dan gelen yanıtı yorumlayabiliyor olmasına dikkat edin.
* Hassas olmayan dataları ve yanıtları loglamaya dikkat edin.
* Entegrasyonunuzun son kullanıcılar için [Kişisel Verilerin Koruması Kanunu](https://dev.iyzipay.com/tr/sss) ile uyumlu olmasına dikkat edin.
* iyzico logolarını sitenize eklemeyi unutmayın. [iyzico logo paketi](https://dev.iyzipay.com/tr/iyzico-logo-pack.zip).
* iyzico entegrasyon ekibinin onayı için [**entegrasyon@iyzico.com**](mailto:entegrasyon@iyzico.com) mail adresi ile iletişime geçin.

