# Create a User

A user is someone who you want to enroll in your system via using his face and other basic details like name, user name etc

{% swagger baseUrl="https://deepfaceauth.signzy.app/deepfaceauth/" path="api/v1/basic/user/create" method="post" summary="create a user" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Access Token of the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerName" type="string" %}
Customer Name given to you by Signzy
{% endswagger-parameter %}

{% swagger-parameter in="body" name="userName" type="string" %}
a unique username you would like to have for the user you are enrolling. No spaces allowed. 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fullName" type="string" %}
the actual name of the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="emailId" type="string" %}
the email id of the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="phoneNumber" type="string" %}
the phone number of the user
{% endswagger-parameter %}

{% swagger-response status="200" description="application/json" %}
```
{
  "status": "200 OK",
  "message": "User successfully created",
  "enrollmentUrl": "https://signzy.app/deepfaceauth/api/v1/iframe/enroll/portal/E9dea9fDE9dF1Df29E65459fBeB3aBAf/7F3eAf85A101dedC9675D10a4De44Ff0"
}
```
{% endswagger-response %}
{% endswagger %}

##

{% tabs %}
{% tab title="Request Schema" %}
```
{
  "customerName": "...userName of the customer provided by Signzy...",
  "userName": "...a unqiue User Name...",
  "fullName": "...Name of the User...",
  "emailId": "...Email ID of the user...",
  "phoneNumber": "...Phone number of the user..."
}
```
{% endtab %}

{% tab title="Response Parameters" %}
| Parameter Name | Parameter Type | Parameter Description                                                                |
| -------------- | -------------- | ------------------------------------------------------------------------------------ |
| status         | string         | status of the request                                                                |
| message        | string         | message for the user                                                                 |
| enrollmentUrl  | string         | the enrollment portal url, which your user should open in browser to enroll his face |
{% endtab %}
{% endtabs %}

