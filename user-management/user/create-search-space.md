---
description: Create a set of users who have similar attributes
---

# Create Search Space

{% swagger baseUrl="https://deepfaceauth.signzy.app/deepfaceauth" path="/api/v1/basic/searchspace/store" method="post" summary="Create Search Space" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
The access token of the customer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="users" type="array" %}
List of users
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="string" %}
Name of the user set
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerName" type="string" %}
Customer Name provided by Signzy
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "message": "Successfully Updated.",
    "status": "200 OK"
}
```
{% endswagger-response %}
{% endswagger %}

