# Check Enrollment Status of a User

This API is to check the enrollment status of a user

{% swagger baseUrl="https://deepfaceauth.signzy.app/deepfaceauth/" path="api/v1/basic/status/enroll/user" method="post" summary="check enrollment of a user" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
.The Access Token for the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerName" type="string" %}
Customer Name given to you by Signzy.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="enrollmentUrl" type="string" %}
The enrollment URL provided when a user is created
{% endswagger-parameter %}

{% swagger-response status="200" description="application/json" %}
```
{
    "userName": "..username..",
    "enrollmentStatus": "...URL...",
    "message": "..status..",
    "status": "... status code.."
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="Request Schema" %}
```
{
  "customerName": "...userName of the customer provided by Signzy...",
  "enrollmentUrl": "https://signzy.xyz/deepfaceauth/api/v1/iframe/enroll/portal/cdAa63C6E0839d67fD1C1aEb189Ba647/35eFA9C86B661cc5FC0e0925FF5aC9Be"
}
```
{% endtab %}

{% tab title="Response Parameter" %}
| Parameter Name   | Parameter Type | Parameter Description                     |
| ---------------- | -------------- | ----------------------------------------- |
| status           | string         | status of the request                     |
| message          | string         | message for the user                      |
| enrollmentStatus | string         | can be one of success \| failure \| draft |
| userName         | string         | User Name assigned or created by a user   |
{% endtab %}
{% endtabs %}

