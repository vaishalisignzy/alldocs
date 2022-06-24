# Update face

This endpoint will be used to update the face image of the user into the system.&#x20;

{% swagger baseUrl="https://deepfaceauth.signzy.app/deepfaceauth" path="/api/v1/basic/update" method="post" summary="Update" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Content-Type " type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Access Token of the customer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerName" type="string" %}
the userName given to you by Signzy.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="url" type="string" %}
The face url of the enrolling user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="enrolledUrl" type="string" %}
The enrolled url provided in the create user request. 
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "userName":"anyname",
  "faceOriginal":"url",
  "faceThumbnail":"url",
  "message": "User is successfully updated",
  "status": "200 OK",
  "enrollmentStatus": "success"
}
```
{% endswagger-response %}

{% swagger-response status="400" description="" %}
```
{
   "error": {
      "userName":"anyname",
      "faceOriginal":"url",
      "faceThumbnail":"url",
      "enrollmentStatus": "failure",
      "message": "User is not registered",
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
    "url": "...url of the face to be registered...",
    "enrolledUrl": "...The URL provided at the time of User creation..."
}
```
{% endtab %}

{% tab title="Response Paramaters" %}
| Paramter Name     | Parameter Type | Parameter Description             |
| ----------------- | -------------- | --------------------------------- |
| username          | string         | unique username of the user       |
| faceOriginal      | string         | The original face URL of the user |
| faceThumbnail     | string         | Zoomed face image of the user     |
| status            | string         | Status of the request             |
| message           | string         | Message for the user              |
| enrollment status | string         | Status of enrollment              |
{% endtab %}
{% endtabs %}

