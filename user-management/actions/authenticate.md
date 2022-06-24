---
description: >-
  This endpoint will be used to authenticate a user into the system with the
  face image which was captured during enrollment
---

# Authenticate face

**Callback**

{% swagger baseUrl="https://deepfaceauth.signzy.app/deepfaceauth" path="/api/v1/basic/authenticate" method="post" summary="Authenticate" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="" type="string" %}

{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Access Token of the customer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerName" type="string" %}
Customer Name was given to you by signzy
{% endswagger-parameter %}

{% swagger-parameter in="body" name="username" type="string" %}
User name of the user to authenticate
{% endswagger-parameter %}

{% swagger-parameter in="body" name="precision" type="string" %}
Keep its value "high" 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerName" type="string" %}
the userName given to you by Signzy.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="url" type="string" %}
URL of the face to authenticate
{% endswagger-parameter %}

{% swagger-parameter in="body" name="useSampleForLearning" type="string" %}
yes or no
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "userName":"anyname",
  "faceOriginal":"url",
  "faceThumbnail":"url",
  "authenticationStatus": "success",
  "message": "User is successfully authenticated",
  "status": "200 OK"
}
```
{% endswagger-response %}

{% swagger-response status="400" description="" %}
```
{
   "error": {
      "userName":"anyname",
      "faceOriginal":"url",
      "authenticationStatus": "failure",
      "message": "User is not authenticated",
      "status": "422"
   }

}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="Request Schema" %}
```
{
    "customerName": "...The username of the customer provided by Signzy...",
    "url": "...URL of the face...",
    "useSampleForLearning": "yes/no",
    "userName": "...unique usernamae of the user...",
    "precision": "high/low"
}
```
{% endtab %}

{% tab title="Response Paramaters" %}
| Paramter Name        | Parameter Type | Parameter Description             |
| -------------------- | -------------- | --------------------------------- |
| username             | string         | unique username of the user       |
| faceOriginal         | string         | The original face URL of the user |
| authenticationStatus | string         | success/failure                   |
| status               | string         | Status of the request             |
| message              | string         | Message for the user              |
| faceThumbnail        | string         | Zoomed face image                 |
{% endtab %}
{% endtabs %}

