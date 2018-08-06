---
description: 'İşlem posa iletildikten sonra, banka tarafından dönen hatalardır.'
---

# Banka Hataları

iyzico ödeme API'sinde bankadan dönen hata mesajları 10bin ile başlar. En çok alınan hata koldarının başına 10bin eklenerek yanıt olarak anında döner. Örnek "10005". 10 bin’den küçük hata kodları ise API'den dönen validasyon ya da business hata kodları olarak adlandırılır.

Bir hata oluştuğunda yani status parametresi failure değeri aldığında iyzico ödeme API'si aşağıdaki gibi yanıt döner:

* **errorCode**: örneğin 10051
* **errorGroup**: örneğin NOT\_SUFFICIENT\_FUNDS
* **errorName**: örneğin Error
* **errorMessage**: örneğin Kart limiti yetersiz, yetersiz bakiye

**Hata Kodları Detayı**

* Eğer hata bankadan dönüyorsa 10binle başlayan hatalar alınır ve hata grubuna göre many-to-many olan hataları iyzico tasnif ederek, API'den döner. Hata grubuna göre \(**hata koduna göre değil, mutlaka grubu kullanın**\) üye iş yeri mapping yapabilir veya yanıt olarak dönen mesajı son kullanıcıya gösterebilir. Örneğin 051 limit yetersiz size 10051 koduyla ve NOT\_SUFFICIENT\_FUNDS grubuyla döner. Tüm liste aşağıdaki gibidir, ek olarak bu işlemleri panelde kırmızı kayıtlar olarak görebilirsiniz.

| **errorCode** | **errorMessage** | **errorGroup** |
| :--- | :--- | :--- |
| 10051 | Kart limiti yetersiz, yetersiz bakiye | NOT\_SUFFICIENT\_FUNDS |
| 10005 | İşlem onaylanmadı | DO\_NOT\_HONOUR |
| 10012 | Geçersiz işlem | INVALID\_TRANSACTION |
| 10041 | Kayıp kart, karta el koyunuz | LOST\_CARD |
| 10043 | Çalıntı kart, karta el koyunuz | STOLEN\_CARD |
| 10054 | Vadesi dolmuş kart | EXPIRED\_CARD |
| 10084 | CVC2 bilgisi hatalı | INVALID\_CVC2 |
| 10057 | Kart sahibi bu işlemi yapamaz | NOT\_PERMITTED\_TO\_CARDHOLDER |
| 10058 | Terminalin bu işlemi yapmaya yetkisi yok | NOT\_PERMITTED\_TO\_TERMINAL |
| 10034 | Dolandırıcılık şüphesi | FRAUD\_SUSPECT |
| 10093 | Kartınız e-ticaret işlemlerine kapalıdır. Bankanızı arayınız. | RESTRICTED\_BY\_LAW |
| 10201 | Kart, işleme izin vermedi | CARD\_NOT\_PERMITTED |
| 10202 | Ödeme işlemi esnasında genel bir hata oluştu | UNKNOWN |
| 10203 | Önceden onaylanan işlem | APPROVED\_COMPLETED |
| 10204 | Ödeme işlemi esnasında genel bir hata oluştu | UNKNOWN |
| 10205 | E-posta geçerli formata değil | INVALID\_CHARS\_IN\_EMAIL |
| 10206 | CVC uzunluğu geçersiz | INVALID\_CVC2\_LENGTH |
| 10207 | Bankanızdan onay alınız | REFER\_TO\_CARD\_ISSUER |
| 10208 | Üye işyeri kategori kodu hatalı | INVALID\_MERCHANT\_OR\_SP |
| 10209 | Bloke statülü kart | BLOCKED\_CARD |
| 10210 | Hatalı CAVV bilgisi | INVALID\_CAVV |
| 10211 | Hatalı ECI bilgisi | INVALID\_ECI |
| 10212 | CVC2 yanlış girme deneme sayısı aşıldı | CVC2\_MAX\_ATTEMPT |
| 10213 | BIN bulunamadı | BIN\_NOT\_FOUND |
| 10214 | İletişim veya sistem hatası | COMMUNICATION\_OR\_SYSTEM\_ERROR |
| 10215 | Geçersiz kart numarası | INVALID\_CARD\_NUMBER |
| 10216 | Bankası bulunamadı | NO\_SUCH\_ISSUER |
| 10217 | Banka kartları sadece 3D Secure işleminde kullanılabilir | DEBIT\_CARDS\_REQUIRES\_3DS |
| 10218 | Banka kartları ile taksit yapılamaz | DEBIT\_CARDS\_INSTALLMENT\_NOT\_ALLOWED |
| 10219 | Bankaya gönderilen istek zaman aşımına uğradı | REQUEST\_TIMEOUT |
| 10220 | Ödeme alınamadı | DECLINED |
| 10221 | Terminal yurtdışı kartlara kapalı | NOT\_PERMITTED\_TO\_FOREIGN\_CARD |
| 10222 | Terminal taksitli işleme kapalı | NOT\_PERMITTED\_TO\_INSTALLMENT |
| 10223 | Gün sonu yapılmalı | REQUIRES\_DAY\_END |
| 10224 | Para çekme limiti aşılmış | EXCEEDS\_WITHDRAWAL\_AMOUNT\_LIMIT |
| 10225 | Kısıtlı kart | RESTRICTED\_CARD |
| 10226 | İzin verilen PIN giriş sayısı aşılmış | EXCEEDS\_ALLOWABLE\_PIN\_TRIES |
| 10227 | Geçersiz PIN | INVALID\_PIN |
| 10228 | Banka veya terminal işlem yapamıyor | ISSUER\_OR\_SWITCH\_INOPERATIVE |
| 10229 | Son kullanma tarihi geçersiz | INVALID\_EXPIRE\_YEAR\_MONTH |
| 10230 | İstek bankadan hata aldı | REQUEST\_BLOCKED\_BY\_BANK |
| 10231 | Satış tutarı ödül puanından düşük olamaz | SALES\_AMOUNT\_LESS\_THAN\_AWARD |
| 10232 | Geçersiz tutar | INVALID\_AMOUNT |
| 10233 | Geçersiz kart tipi | INVALID\_CARD\_TYPE |
| 10234 | Yetersiz ödül puanı | NOT\_SUFFICIENT\_AWARD |
| 10235 | American Express kart hatası | AMEX\_CAN\_USE\_ONLY\_MR |
| 10236 | Ödeme işlemi esnasında genel bir hata oluştu | UNKNOWN |

