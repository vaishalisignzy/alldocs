# Whitelist a User

Whitelist a user means to make a blacklisted user able to access your services again

{% swagger baseUrl="https://deepfaceauth.signzy.app/deepfaceauth" path="/api/v1/basic/user/whitelist" method="post" summary="whitelist a user" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
The Access Token for the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerName" type="string" %}
the userName given to you by Signzy
{% endswagger-parameter %}

{% swagger-parameter in="body" name="userName" type="string" %}
a unique username you had registered
{% endswagger-parameter %}

{% swagger-response status="200" description="application/json" %}
```
{
  "status": "200 OK",
  "message": "User successfully whitelisted"
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="Request Schema" %}
```
{
  "customerName": "...userName of the customer provided by Signzy...",
  "userName": "...a unqiue User Name you had registered..."
}
```
{% endtab %}

{% tab title="Response Parameter" %}
| status  | string | status of the request |
| ------- | ------ | --------------------- |
| message | string | message for the user  |
| status  | string | status of the request |


{% endtab %}
{% endtabs %}
