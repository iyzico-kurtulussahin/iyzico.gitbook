---
description: >-
  iyzico'nun ödeme formunu veya API'sini entegre etmek için gerekli kodlara
  buradan ulaşabilirsiniz.
---

# Yazılım bilgisi gerekli

### **İstemci\(client\) seçimi**

iyzico entegrasyon için, sunucu taraflı programlama diline uygun 6 farklı istemci\(client\) sunar. Bu istemcilerden programlama yapmak istediğiniz dile uygun olanı seçip sandbox\(test\) bilgileri ile kullanmaya başlayabilirsiniz.

{% hint style="info" %}
Kütüphanelerimize ve kod örneklerimize [github iyzico hesabı](https://github.com/iyzico) üzerinden ulaşabilirsiniz.

Ek olarak Composer, Nuget, Maven, pip, gem, npm üzerinden iyzipay yazıp projelerinize dahil edebilirsiniz.
{% endhint %}

[![PHP](https://dev.iyzipay.com/user/pages/01.baslarken/01_php.png)](https://github.com/iyzico/iyzipay-php/releases/latest) [![.NET](https://dev.iyzipay.com/user/pages/01.baslarken/02_.net.png)](https://github.com/iyzico/iyzipay-dotnet/releases/latest) [![JAVA](https://dev.iyzipay.com/user/pages/01.baslarken/05_java.png)](https://github.com/iyzico/iyzipay-java/releases/latest) [![NODE](https://dev.iyzipay.com/user/pages/01.baslarken/06_node.png)](https://github.com/iyzico/iyzipay-node/releases/latest) [![RUBY](https://dev.iyzipay.com/user/pages/01.baslarken/04_ruby.png)](https://github.com/iyzico/iyzipay-ruby/releases/latest) [![PYTHON](https://dev.iyzipay.com/user/pages/01.baslarken/03_pyton.png)](https://github.com/iyzico/iyzipay-python/releases/latest)

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

