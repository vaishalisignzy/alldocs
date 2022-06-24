# View Blacklisted Users

To view all the users that are blacklisted to use the service.

{% swagger baseUrl="https://preproduction-ai.signzy.app/deepfaceauth" path="/api/v1/basic/view/blacklist/all" method="get" summary="view blacklisted users" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Access Token for the user
{% endswagger-parameter %}

{% swagger-response status="200" description="application/json" %}
```
{
  "status": "200 OK",
  "message": "success",
  "data": [
    {
      "userName": "a unqiue User Name you had registered",
      "fullName": "the actual name of the user",
      "emailId": "the email id of the user",
      "phoneNumber": "the phone number of the user",
      "faceThumbnail": "face image of the user",
      "faceOriginal": "thumbnail face image of the user",
      "timeStamp": "2019-06-04 18:17:40"
    }
  ]
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="Request Parameter" %}
| Parameter Name | Parameter Type | Parameter Description                   |
| -------------- | -------------- | --------------------------------------- |
| customerName   | String         | Customer Name provided to you by Signzy |
{% endtab %}

{% tab title="Response Parameter" %}
| Parameter Name | Parameter Type   |  Parameter Description |
| -------------- | ---------------- | ---------------------- |
| status         | string           | status of the request  |
| message        | string           | message for the user   |
| data           | array of objects | List of users          |


{% endtab %}
{% endtabs %}

