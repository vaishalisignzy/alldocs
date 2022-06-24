---
description: >-
  If the user no longer wants to use the service he/she can delete his access
  account by specifying the customer name and the username of the user.
---

# Delete a User

{% swagger baseUrl="https://deepfaceauth.signzy.app/deepfaceauth" path="/api/v1/basic/user/delete" method="post" summary="delete a user" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Access Token of the user
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
  "message": "Successfully deleted"
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

