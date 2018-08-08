---
description: >-
  iyzico'nun ödeme formunu veya API'sini entegre etmek için gerekli kodlara
  buradan ulaşabilirsiniz.
---

# Yazılım bilgisi gerekli

iyzico ödeme API’si, internet üzerinden ödeme kabul eden tüm üye işyerlerine ihtiyacına cevap verecek şekilde, oturum bilgisi tutmayan \(stateless\) Restful servis odaklı bir mimaride geliştirilmiştir. iyzico'nun sunduğu sunucu taraflı programlama diline uygun istemciler \(client\) ile çok kolay entegre olunabilir. 

### **iyzico github Sayfası**

{% page-ref page="../sss/teknik-sorular/github.com-iyzico.md" %}

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

