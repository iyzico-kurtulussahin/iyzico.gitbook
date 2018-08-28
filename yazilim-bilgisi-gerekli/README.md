---
description: >-
  Yazılım geliştirme ekibiniz entegrasyon için gerekli yönlendirmelere buradan
  ulaşabilir.
---

# Yazılım bilgisi gerekli

## Genel Bilgi

iyzico'yu sitenize entegre etmenin en hızlı yolu ödeme formunu kullanmaktır. iyzico'nun hazırlamış olduğu kütüphaneler ile 2 adet basit sorguyu projelerinizde kullanabilirsiniz.

{% hint style="warning" %}
Bu entegrasyonu yapabilmeniz için iyzico hesabınıza giriş yaptıktan sonra [Firma Ayarları](https://merchant.iyzipay.com/merchant-settings) menüsünde **API** ve **Güvenlik** anahtarlarını görebiliyor olmanız gerekmektedir. Eğer anahtarları göremiyor iseniz başvurunuz konusunda destek ekibi ile iletişime geçebilirsiniz.
{% endhint %}

## Nasıl Çalışır ?

iyzico sürekli gelişmekte olan kapsamlı bir Sandbox \(Test\) ortamı sunar. Sandbox ortamında hesap oluşturmak için[ bu bağlantıyı](https://sandbox-merchant.iyzipay.com/auth/register) kullanabilirsiniz. Test ortamında test kartları ile kullanılmak üzere API ve Güvenlik anahtarlarınıza, email adresiniz ile kayıt oluşturup, panelinizin "Ayarlar-&gt;Firma Ayarları" bölümünden ulaşabilirsiniz.

{% hint style="danger" %}
iyzico'da 2 farklı ortam bulunmaktadır. Canlı \(Live\) ortam ve Sandbox \(Test\) ortamı. **Canlı**  kontrol panelinizden erişebileceğiniz API ve Güvenlik anahtarları, **Sandbox** kontrol panelinizdekilerden farklıdır. Bu nedenden dolayı iki ortamın baseUrl değerleri aşağıdaki gibidir. Bu değerleri **kütüphanenizdeki** config dosyasında kullanabilirsiniz.

**Canlı** ortamtaki anahtarlar için **\(Live\)** : **`https://api.iyzipay.com`**

**Sandbox** ortamındaki anahtarlar için **\(Test\)** :**`https://sandbox-api.iyzipay.com`**
{% endhint %}

## Hadi Başlayalım

Yazılım geliştirmede kullandığınız programlama diline uygun kütüphaneyi [github hesabımızdan](https://github.com/iyzico) indirebilir veya kullandığınız dilin paket yöneticisi ile projenize ekleyebilirsiniz.

| Programlama Dili | Paket Yöneticisi | Github Sayfası |
| :--- | :--- | :--- |
| PHP | composer -&gt; iyzipay | [https://github.com/iyzico/iyzipay-php](https://github.com/iyzico/iyzipay-php) |
| C\# | nuget -&gt; iyzipay | [https://github.com/iyzico/iyzipay-dotnet](https://github.com/iyzico/iyzipay-dotnet) |
| Java | maven -&gt; iyzipay | [https://github.com/iyzico/iyzipay-java](https://github.com/iyzico/iyzipay-java) |
| Node | npm -&gt; iyzipay | [https://github.com/iyzico/iyzipay-node](https://github.com/iyzico/iyzipay-node) |
| Ruby | gem -&gt; iyzipay | [https://github.com/iyzico/iyzipay-ruby](https://github.com/iyzico/iyzipay-ruby) |
| Python | pip -&gt; iyzipay | [https://github.com/iyzico/iyzipay-python](https://github.com/iyzico/iyzipay-python) |

## Entegrasyon Methodları

iyzico'yu iki şekilde entegre edebilirsiniz.

Hızlı ve kolay bir şekilde ödeme almaya başlamak ise  ödeme formunu tercih edilebilirsiniz. Ön yüz kontrolleri \(validasyon\), BIN numarası sorgulama, Taksit yönetimi, 3D Secure ile ödeme, BKM Express, Fraud ve işlem limitleri için ek sorgu yapmaya gerek kalmadan tek bir entegrasyon ile işlemler tamamlanır.  Rehbere ulaşmak için [**tıklayınız**](https://google.com).



Eğer PCI SAQ-D formunu dolduruyor iseniz kendi tasarımınız olan ödeme formunuzu API aracılığı ile entegre edebilirsiniz.

{% hint style="info" %}
Bu sayfa ile ilgili sorunuz var ise `destek@iyzico.com` adresinden bizim ile iletişime geçebilirsiniz.
{% endhint %}



