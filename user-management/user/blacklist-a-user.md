# Blacklist a User

Blacklisting a user means to deny access to that user to further not use the service.

{% swagger baseUrl="https://deepfaceauth.signzy.app/deepfaceauth" path="/api/v1/basic/user/blacklist" method="post" summary="blacklist a user" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
The access token for the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerName" type="string" %}
Customer Name was given to you by Signzy.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="userName" type="string" %}
a unique username you had registered
{% endswagger-parameter %}

{% swagger-response status="200" description="application/json" %}
```
{
  "status": "200 OK",
  "message": "User successfully blacklisted"
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
| Parameter Name | Parameter Type | Parameter Description |
| -------------- | -------------- | --------------------- |
| status         | string         | status of the request |
| message        | string         | message for the user  |
{% endtab %}
{% endtabs %}

