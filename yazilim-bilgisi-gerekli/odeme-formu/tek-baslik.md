---
description: >-
  iyzico'nun ödeme formu teknolojisini 2 basit sorgu ile entegre edebilirsiniz.
  Sizler için 1 adet entegrasyon videosu hazırladık ve popüler olan PHP dilini
  kullandık.
---

# Tek Başlık

### test

{% api-method method="post" host="https://api.iyzipay.com" path="/payment/iyzipos/checkoutform/initialize/auth/ecom" %}
{% api-method-summary %}
Formu Oluşturma
{% endapi-method-summary %}

{% api-method-description %}
Form Oluşturma sorgusunu kütüphanelerimizde yer alan sample klasörü içerisinde bulabilirsiniz. Composer, Nuget, Maven, pip, gem üzerinden iyzipay yazıp projelerinize dahil edebileceğiniz gibi github üzerinden bilgisayarınıza kaynak kodları indirebilirsiniz.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="Authorization" type="string" required=true %}
Authentication token to track down who is emptying our stocks.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="locale" type="string" %}
türkçe için tr ve ingilizce için en parametrelerini kullanabilirsiniz. Diğer diller zamanla eklenecektir. Changelog sayfasını takip ediniz.
{% endapi-method-parameter %}

{% api-method-parameter name="conversationId" type="boolean" %}
ilgili işlemi daha sonra tekrar sorgulamanıza yarayacak sipariş numarası alanıdır.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
{
    "name": "Cake's name",
    "recipe": "Cake's recipe name",
    "cake": "Binary cake"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```javascript
{
    "message": "Ain't no cake like that."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



