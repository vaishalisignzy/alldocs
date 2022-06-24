# Merchant Creation

{% swagger baseUrl="https://go-preproduction.signzy.app" path="/api/applications/:applicationId/merchants" method="post" summary="Create Merchant" %}
{% swagger-description %}
This API can be called by a logged in Backops User. After the backops user logs in, the response gets authentication token and application id which is used in this request.
{% endswagger-description %}

{% swagger-parameter in="path" name="applicationId" type="string" %}
Application Id returned after backops user login.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Access token returned from backops login request.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fields" type="object" %}
Meta-Data object about the merchant
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobile" type="string" %}
Merchant mobile number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="realm" type="string" %}
Domain context for the merchant
{% endswagger-parameter %}

{% swagger-parameter in="body" name="flowId" type="string" %}
Flow Id for Merchant KYC
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="string" %}
Merchant Name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" type="string" %}
Merchant Email Id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="username" type="string" %}
Merchant username used for login
{% endswagger-parameter %}

{% swagger-parameter in="body" name="password" type="string" %}
Merchant password used during login along with username
{% endswagger-parameter %}

{% swagger-response status="200" description="Merchant Successfully Created" %}
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

{% swagger-response status="400" description="Realm parameter not provided. Realm is a required parameter" %}
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

{% swagger-response status="401" description="Unauthorized Access by the backops user." %}
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

#### Sample request-response and field description

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

| Key      | Type   | Description                               |
| -------- | ------ | ----------------------------------------- |
| name     | string | Name of the merchant                      |
| email    | string | Merchant Email Id                         |
| username | string | Merchant username                         |
| password | string | Merchant password                         |
| mobile   | string | Merchant Mobile Number                    |
| realm    | string | Domain the merchant is mapped to          |
| flowId   | string | Onboarding Flow the merchant is tagged to |
{% endtab %}

{% tab title="Sample Response Body" %}
```
{
    "name": "...name...",
    "username": "...username...",
    "email": "...email...",
    "mobile": "...mobile...",
    "flowId": "...flowId...",
    "realm": "...realm...",
    "signzyAppId": "...signzyAppId...",
    "id": "...id...",
    "applicationId": "...applicationId...",
    "fields": "...fields...",
        "branch": "...branch...",
        "region": "...region...",
    },
    "onboardingStartDate": ...onboardingStartDate...,
    "status": "...status...",
    "autoLoginUrl": "...autoLoginUrl...",
    "backopsUserId": "...backopsUserId...",
    "flowDetails": {"...flowDetails..."}
}
```

#### Response Field Description

| Key                 | Type   | Description                                            |
| ------------------- | ------ | ------------------------------------------------------ |
| name                | string | Name of the merchant created                           |
| username            | string | Username of the merchant created                       |
| email               | string | Email Id of the created Merchant                       |
| flowId              | string | FlowId assigned for this merchant                      |
| realm               | string | Realm (domain) assigned for this merchant              |
| signzyAppId         | number | Signzy User Id assigned to the merchant                |
| id                  | string | Merchant Id                                            |
| applicationId       | string | Application Id to which the merchant is tagged to      |
| fields              | object | Merchant Meta-Information                              |
| onboardingStartDate | number | Onboarding Start Date in Epoch Time                    |
| status              | string | Status of the merchant                                 |
| autoLoginUrl        | string | URL through which the merchant can automatically login |
| backOpsUserId       | string | User Id of the backops user who created the merchant   |
| flowDetails         | object | Details of the flow.                                   |
{% endtab %}
{% endtabs %}
