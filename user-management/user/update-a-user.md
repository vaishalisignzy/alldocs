# Update User Details

Update a user means is to update the details of the user which includes his username, email ID, full name & face of the user&#x20;

{% swagger baseUrl="https://deepfaceauth.signzy.app/deepfaceauth" path="/api/v1/basic/user/update" method="post" summary="update a user" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
The Access Token of the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerName" type="string" %}
Customer name was given to you by Signzy.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="userName" type="string" %}
a unique username you had registered
{% endswagger-parameter %}

{% swagger-parameter in="body" name="faceToBeUpdated" type="string" %}
whether face also needs to be updated. Either yes or no.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="parametersToBeUpdated" type="object" %}
The object consists of a user name, full name, email ID, and phone number for updation.
{% endswagger-parameter %}

{% swagger-response status="200" description="application/json" %}
```
{
  "status": "200 OK",
  "message": "User successfully updated",
  "reEnrollmentUrl": "... URL to reenroll the user..."
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="Request Schema" %}
```
{
  "customerName": "...userName of the customer provided by Signzy...",
  "userName": "...a unqiue User Name you had registered...",
  "faceToBeUpdated": "yes",
  "parametersTobeUpdated": {
    "userName": "...a unqiue User Name...",
    "fullName": "any name",
    "emailId": "some@eamil.com",
    "phoneNumber": "1234567890"
  }
}
```
{% endtab %}

{% tab title="Response Parameter" %}
| Parameter Name  | Parameter Type | Parameter Description                                                                |
| --------------- | -------------- | ------------------------------------------------------------------------------------ |
| status          | string         | status of the request                                                                |
| message         | string         | message for the user                                                                 |
| reEnrollmentUrl | string         | if faceToBeUpdated is yes in the request, then a new re-enroll URL will be generated |
{% endtab %}
{% endtabs %}
