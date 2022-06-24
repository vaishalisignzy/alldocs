# Logout - Delete an Access Token



{% swagger baseUrl="https://deepfaceauth.signzy.app/deepfaceauth" path="/api/v1/basic/logout" method="post" summary="Logout-delete an access token" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Conten-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerName" type="string" %}
Customer Name given to you by Signzy
{% endswagger-parameter %}

{% swagger-parameter in="body" name="accessToken" type="string" %}
accessToken you want to logout
{% endswagger-parameter %}

{% swagger-response status="200" description="application/json" %}
```
{
  "status": "200 OK",
  "message": "Successfully logged out"
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="Request Schema" %}
```
{
  "accessToken": "...accessToken you want to logout...",
  "customerName": "...name of the customer..."
}
```
{% endtab %}

{% tab title="Response Parameter" %}
| Parameter Name | Parameter Type  | Parameter Description |
| -------------- | --------------- | --------------------- |
| status         | string          | status of the request |
| message        | string          | message of the user   |
{% endtab %}
{% endtabs %}
