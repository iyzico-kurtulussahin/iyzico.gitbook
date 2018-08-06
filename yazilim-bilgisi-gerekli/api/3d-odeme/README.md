---
description: 3d başlatma ve 3d tamamlama olarak iki adet sorgu kullanılır.
---

# 3d Ödeme

Kendi ödeme formunuzu kullanıyor iseniz, 3ds entegrasyonu aşağıdaki 2 sorgudan oluşmaktadır. 

{% page-ref page="3d-baslatma.md" %}

{% page-ref page="3d-tamamlama.md" %}

{% hint style="info" %}
Bir 3ds başlatma isteği yapıldığında, dönen cevap içerisindeki _**`threedsHtmlContent`**_ parametresinde, kullanıcıyı kart bankasının 3ds güvenlik ekranına  yönlendirecek script bulunur.

Bu scripti, kart sahibinin gördüğü ekrana ilettiğiniz anda, tarayıcı kart sahibini, bankasının 3ds güvenlik ekranına yönlendirecek ve bu sayfada kart sahibi ile kart bankası başbaşa olacaktır.

Kart sahibi 3ds güvenlik şifresini girdikten sonra otomatik olarak callbackUrl parametresinde belirttiğiniz adrese yönlenecek ve iyzico bu adrese [**"CallbackUrl adresine post edilen değerler"**](https://iyzico.gitbook.io/tr/yazilim-bilgisi-gerekli/api/untitled/3d-baslatma#callbackurl-adresine-post-edilen-degerler) ****kısmında belirtilen parametreleri post edecektir.

Bu parametreler kullanılarak, 3ds sürecinin 2. sorgusu olan [**"3d Tamamlama"**](https://iyzico.gitbook.io/tr/~/edit/drafts/-LIQ8LK5CI4WiMXnccFe/yazilim-bilgisi-gerekli/api/untitled/3d-tamamlama) ****sorgusu ****yapılmalıdır. ilk adım sadece 3d güvenlik onayı içindir, 2. sorgu olan "3d tamamlama" sorgusu para çekme işlemi içindir.  "3d tamamlama" sorgusu yapılmadan karttan tutar çekilmeyecektir.
{% endhint %}

{% hint style="info" %}
Ayrıntılı bilgiler, açıklamalar ve parametreler için [**"3d başlatma"**](https://iyzico.gitbook.io/tr/yazilim-bilgisi-gerekli/api/untitled/3d-baslatma) ve [**"3d Tamamlama"**](https://iyzico.gitbook.io/tr/yazilim-bilgisi-gerekli/api/untitled/3d-baslatma) sayfalarını ziyaret etmeyi unutmayınız.
{% endhint %}

