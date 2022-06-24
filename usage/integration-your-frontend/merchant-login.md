# Merchant Login

{% swagger baseUrl="https://go-preproduction.signzy.app" path="/api/merchants/login" method="post" summary="Merchant Login" %}
{% swagger-description %}
This endpoint is used to login a merchant. If successful the merchant authorization token is received in `id` of the response.
{% endswagger-description %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="body" name="username" type="string" %}
merchant's username
{% endswagger-parameter %}

{% swagger-parameter in="body" name="realm" type="string" %}
realm of the merchant
{% endswagger-parameter %}

{% swagger-parameter in="body" name="password" type="string" %}
merchant's password 
{% endswagger-parameter %}

{% swagger-response status="200" description="Successful Login" %}
```
{
    "id": "...id...",
    "ttl": "...ttl...",
    "created": "...created...",
    "userId": "...userId...",
    "data": {
        "name": "...name...",
        "email": "...email...",
        "mobile": "...mobile...",
        "flowId": "...flowId...",
        "realm": "...realm...",
        "signzyAppId": "...signzyAppId...",
        "applicationId": "...applicationId...",
        "onboardingStartDate": "...onboardingStartDate...",
        "status": "...status...",
        "backopsUserId": "...backopsUserId...",
        "landingPage": "...landingPage...",
        "flowDetails": "...flowDetails...",
        "hideEmailOnboardingOption": "...hideEmailOnboardingOption...",
        "flowRedirectUrl": "...flowRedirectUrl...",
        "hideLogout": "...hideLogout...",
        "theme": "...theme..."
    }
}
```
{% endswagger-response %}

{% swagger-response status="400" description="Realm not found" %}
```
{
    "error": {
        "statusCode": 400,
        "name": "SyntaxError",
        "message": "Unexpected token } in JSON at position 58"
    }
}
```
{% endswagger-response %}

{% swagger-response status="401" description="Login Failed" %}
```
{
    "error": {
        "statusCode": 401,
        "name": "Error",
        "message": "login failed",
        "code": "LOGIN_FAILED"
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
	"username" : "...username...",
	"password" : "...password...",
	"realm": "...realm..."
}
```

#### Request Field Description

| Key      | Type   | Description                                   |
| -------- | ------ | --------------------------------------------- |
| username | string | Username of the merchant                      |
| password | string | Merchant's password for the provided username |
| realm    | string | Merchant's realm (Domain)                     |
{% endtab %}

{% tab title="Sample Response Body" %}
```
{
    "id": "...id...",
    "ttl": "...ttl...",
    "created": "...created...",
    "userId": "...userId...",
    "data": {
        "name": "...name...",
        "email": "...email...",
        "mobile": "...mobile...",
        "flowId": "...flowId...",
        "realm": "...realm...",
        "signzyAppId": "...signzyAppId...",
        "applicationId": "...applicationId...",
        "onboardingStartDate": "...onboardingStartDate...",
        "status": "...status...",
        "backopsUserId": "...backopsUserId...",
        "landingPage": "...landingPage...",
        "flowDetails": "...flowDetails...",
        "hideEmailOnboardingOption": "...hideEmailOnboardingOption...",
        "flowRedirectUrl": "...flowRedirectUrl...",
        "hideLogout": "...hideLogout...",
        "theme": "...theme..."
    }
}
```

#### Response Field Description

| Key                              | Type    | Description                                                                   |
| -------------------------------- | ------- | ----------------------------------------------------------------------------- |
| id                               | string  | Authentication token for the merchant generated after login                   |
| ttl                              | int     | **Time To Live.** Number of seconds the authentication token is valid.        |
| created                          | string  | Time stamp (Date format) when the merchant was created.                       |
| userId                           | string  | Signzy database user id                                                       |
| **data**                         | object  | Object containing information about the application flow and merchant         |
| data._name_                      | string  | Name of the merchant                                                          |
| data._email_                     | string  | Email id of the merchant                                                      |
| data. _mobile_                   | string  | Merchant Mobile Number                                                        |
| data._flowId_                    | string  | Signzy Flow Id defined for the merchant                                       |
| data._realm_                     | string  | Realm of the merchant                                                         |
| data._signzyAppId_               | string  | Id of the App registered in Signzy.                                           |
| data._applicationId_             | string  | Id of the application assigned to the Application                             |
| data._onboardingStartDate_       | int     | Epoch time when the merchant was created and the on-boarding process started. |
| data._status_                    | string  | Status of the merchant on-boarding.                                           |
| data._backopsUserId_             | string  | Backops user who created the merchant                                         |
| data._landingPage_               | string  | The first page on landing after login.                                        |
| data._flowDetails_               | object  | Description about the flow assigned to the merchant                           |
| data._hideEmailOnboardingOption_ | boolean | Flag to hide email on-boarding option.                                        |
| data._flowRedirectUrl_           | string  | URL for flow to redirect to                                                   |
| data._hideLogout_                | boolen  | Flag to show and hide logout option                                           |
| data._theme_                     | object  | Theme object for the flow.                                                    |
{% endtab %}
{% endtabs %}
