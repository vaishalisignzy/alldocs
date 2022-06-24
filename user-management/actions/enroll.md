# Enroll face

This endpoint will be used to enroll/register the face of a user into the system.&#x20;

{% swagger baseUrl="https://deepfaceauth.signzy.app/deepfaceauth" path="/api/v1/basic/enroll" method="post" summary="Enroll Face" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Access token of the customer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerName" type="string" %}
Customer Name was given to you by Signzy.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="url" type="string" %}
The face URL of the user to be registered
{% endswagger-parameter %}

{% swagger-parameter in="body" name="enrolledUrl" type="string" %}
The enrollment URL provided at the time of User creation
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "userName":"...unique username of the user...",
  "faceOriginal":"url",
  "faceThumbnail":"url",
  "enrollmentStatus": "success",
  "message": "User is successfully enrolled",
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
      "faceThumbnail":"url",
      "enrollmentStatus": "failure",
      "message": "User is already registered",
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
| Paramter Name    | Parameter Type | Parameter Description             |
| ---------------- | -------------- | --------------------------------- |
| username         | string         | unique username of the user       |
| faceOriginal     | string         | The original face URL of the user |
| faceThumbnail    | string         | Zoomed Photo of the face          |
| enrollmentStatus | string         | success/failure                   |
| status           | string         | Status of the request             |
| message          | string         | Message for the user              |
{% endtab %}
{% endtabs %}

