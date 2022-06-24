# View User Details

View user details include viewing the details of the user such as full name, email id, enrollment URL, country code & phone number

{% swagger baseUrl="https://deepfaceauth.signzy.app/deepfaceauth" path="/api/v1/basic/user/details" method="post" summary="View User Details" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Access Token of the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerName" type="string" %}
Customer Name was given to you by Signzy
{% endswagger-parameter %}

{% swagger-parameter in="body" name="userName" type="string" %}
a unique username you had registered while creating a user   
{% endswagger-parameter %}

{% swagger-response status="200" description="application/json" %}
```
{
    "userName": "..username..",
    "fullName": "..fullname..",
    "emailId": "..emailid..",
    "phoneNumber": "..phonenumber..",
    "countryCode": "..countrycode..",
    "enrollmentUrl": "..url",
    "message": "success",
    "status": "200 OK"
}
```
{% endswagger-response %}
{% endswagger %}



{% tabs %}
{% tab title="Request Schema" %}
```
{
  "customerName": "...userName of the customer provided by Signzy...",
  "userName": "...a unqiue User Name you had registered..."
}
```
{% endtab %}

{% tab title="Response Parameters" %}
| Parameter Name | Parameter Type | Parameter Description                                 |
| -------------- | -------------- | ----------------------------------------------------- |
| status         | string         | Status of the Request                                 |
| message        | string         | Message for the user                                  |
| userName       | string         | a unique username you would like to have for the user |
| fullName       | string         | the actual name of the user                           |
| emailId        | string         | the email id of the user                              |
| phoneNumber    | string         | the phone number of the user                          |
| enrollmentUrl  | string         | enrollment Url of the user                            |
| countryCode    | string         | the country which the phone number belongs to         |
{% endtab %}
{% endtabs %}

