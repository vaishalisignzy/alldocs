# View Search Space

{% swagger baseUrl="https://deepfaceauth.signzy.app/deepfaceauth" path="/api/v1/basic/view/searchspace/user?Autho" method="post" summary="View Search Spa" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
The Auth token of the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="string" %}
name of the list 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerName" type="string" %}
Name provided to you by Signzy
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "data": [
        "shristy",
        "rithik",
        "himani",
        "prachi",
        "chandru"
    ],
    "message": "success.",
    "status": "200 OK"
}
```
{% endswagger-response %}
{% endswagger %}

