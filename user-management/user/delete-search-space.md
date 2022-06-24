---
description: Delete a set of users who have similar attributes
---

# Delete Search Space

{% swagger baseUrl="https://deepfaceauth.signzy.app/deepfaceauth" path="/api/v1/basic/searchspace/delete" method="post" summary="Delete Search Space" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Auth token of the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerName" type="string" %}
Customer Name provided by Signzy
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="string" %}
name of the list
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "message": "Successfully Deleted",
    "status": "200 OK"
}
```
{% endswagger-response %}
{% endswagger %}

