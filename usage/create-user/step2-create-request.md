# Step2  : Create Request

{% swagger baseUrl="https://go-preproduction.signzy.app" path="/api/applications/:applicationId/merchants" method="post" summary="Create User" %}
{% swagger-description %}
Method to create new user for your application
{% endswagger-description %}

{% swagger-parameter in="path" name="applicationId" type="string" %}
applicationId returned from the the backops user

\


login
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
access-token returned from backops login request
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="body" name="flowId" type="string" %}
Flow that is assigned to the end user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="string" %}
name of the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="username" type="string" %}
username for the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="password" type="string" %}
password of the user 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobile" type="string" %}
mobile number of the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" type="string" %}
email of the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="realm" type="string" %}
realm returned from the backops login request
{% endswagger-parameter %}

{% swagger-response status="200" description="Successful user creation." %}
```
{
    "name": "..name..",
    "username": "..username..",
    "email": "..email..",
    "mobile": "..mobile..",
    "realm": "..realm..",
    "signzyAppId": "..signzyAppId..",
    "id": "..id..",
    "applicationId": "..applicationId..",
    "status": "..status..",
    "autoLoginUrl": "..autoLoginUrl..",
    "backopsUserId": "..backopsUserId..",
    "flowId" : "..flowId..",
    "flowDetails" : "..flowDetails.."
}
```
{% endswagger-response %}

{% swagger-response status="400" description="Need to pass realm parameter." %}
```
{
    "error": {
        "statusCode": 400,
        "name": "Error",
        "message": "realm is required",
        "code": "REALM_REQUIRED"
    }
}
```
{% endswagger-response %}

{% swagger-response status="401" description="Need to check the credentials." %}
```
{
   "error": {
       "statusCode": 401,
       "name": "Error",
       "message": "Authorization Required",
       "code": "AUTHORIZATION_REQUIRED"
   }
}
```
{% endswagger-response %}
{% endswagger %}

### Sample request-response and field description

{% tabs %}
{% tab title="Sample Request Body" %}
```
{
    "name": "..name..",
    "email": "..email..",
    "username": "..username..",
    "password": "..password..",
    "mobile": "..mobile..",
    "realm": "..realm..",
    "flowId" : "..flowId.."
}
```

#### Request Field Description

| Key      | Type   | Description                                               |
| -------- | ------ | --------------------------------------------------------- |
| name     | string | Name for the end user whose onboarding has been conducted |
| username | string | Username of the end user                                  |
| password | string | Password of the end user                                  |
| email    | string | Email for the end user                                    |
| mobile   | string | Phone for the end user                                    |
| realm    | string | Realm returned from the backops user login                |
| flowId   | string | Flow that is assigned to the end user                     |
{% endtab %}

{% tab title="Sample Response Body" %}
```
{
    "name": "..name..",
    "username": "..username..",
    "email": "..email..",
    "mobile": "..mobile..",
    "realm": "..realm..",
    "signzyAppId": "..signzyAppId..",
    "id": "..id..",
    "applicationId": "..applicationId..",
    "status": "..status..",
    "backopsUserId": "..backopsUserId..",
    "flowId" : "..flowId..",
    "flowDetails" : "..flowDetails.."
}
```

#### Response Field Descriptions

| Key           | Type   | Description                                             |
| ------------- | ------ | ------------------------------------------------------- |
| name          | string | Name for the end user                                   |
| username      | string | Username of the end user                                |
| email         | string | Email for the end user                                  |
| mobile        | string | Phone for the end user                                  |
| realm         | string | Realm returned from the backops user login              |
| id            | string | Unique identifier of the user (merchantId)              |
| applicationId | string | Your application Id                                     |
| signzyAppId   | number | Merchant Signzy Application Id                          |
| status        | string | Status of the end user, will be "new" for new users     |
| backopsUserId | string | Ids for backops user to which this merchant is assigned |
{% endtab %}
{% endtabs %}
