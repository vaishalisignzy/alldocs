# Step3  : Merchant User Login

{% swagger baseUrl="https://go-preproduction.signzy.app" path="/api/merchants/login" method="post" summary="Merchant Login" %}
{% swagger-description %}
Login method for the merchant user
{% endswagger-description %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="body" name="realm" type="string" %}
domain name in onboarding system 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="username" type="string" %}
username of the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="password" type="string" %}
password of the user
{% endswagger-parameter %}

{% swagger-response status="200" description="Login successful." %}
```
{
    "id": "...id...", //merchant auth token
    "ttl": "...ttl...",
    "created": "...created...",
    "userId": "...userId...", //merchantId
    "data": {
        "name": "...name...",
        "email": "...email...",
        "mobile": "...mobile...",
        "flowId": "...flowId...",
        "realm": "...realm...",
        "applicationId": "...applicationId...",
        "status": "...status...",
        "backopsUserId": "...backopsUserId...",
        "landingPage": [{
                "pageName": "...pageName...",
                "id": "...id...",
                "type": "...type..."
            },
            {
                "pageName": "...pageName...",
                "id": "...id...",
                "type": "...type..."
            },
            {
                "pageName": "...pageName...",
                "id": "...id...",
                "type": "...type..."
            }
        ]
    }
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

{% swagger-response status="401" description="" %}
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
    "username": "..username..",
    "password": "..password..",
    "realm": "..realm.."
}
```

#### Request Field Description

| Key      | Type   | Description                                                   |
| -------- | ------ | ------------------------------------------------------------- |
| username | string | Username of the backops user                                  |
| password | string | Password of the backops user                                  |
| realm    | string | <p>Your domain name for the Onboarding<br>systems account</p> |
{% endtab %}

{% tab title="Sample Response Body" %}
```
{
    "id": "...id...", //merchant auth token
    "ttl": "...ttl...",
    "created": "...created...",
    "userId": "...userId...", //merchantId
    "data": {
        "name": "...name...",
        "email": "...email...",
        "mobile": "...mobile...",
        "flowId": "...flowId...",
        "realm": "...realm...",
        "applicationId": "...applicationId...",
        "status": "...status...",
        "backopsUserId": "...backopsUserId...",
        "landingPage": [{
                "pageName": "...pageName...",
                "id": "...id...",
                "type": "...type..."
            },
            {
                "pageName": "...pageName...",
                "id": "...id...",
                "type": "...type..."
            },
            {
                "pageName": "...pageName...",
                "id": "...id...",
                "type": "...type..."
            }
        ]
    }
}
```

#### Response Field Descriptions

| Key           | Type             | Description                                                                                                                                        |
| ------------- | ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| id            | string           | This is your access token to be passed into other endpoints as an Authorization header                                                             |
| ttl           | number           | <p><strong>Time to live</strong> for your token, which means</p><p>for how much time this token will be valid from the time of </p><p>creation</p> |
| created       | string           | Time and Date of creation of access-token                                                                                                          |
| userId        | string           | Id of the merchant user                                                                                                                            |
| data          | object           | Contains the meta-data about the backops                                                                                                           |
| name          | string           | Name of the merchant user                                                                                                                          |
| mobile        | string           | Mobile number of merchant user                                                                                                                     |
| applicationId | string           | This is the Id to be passed in Pull All Data API, the identifier for the application                                                               |
| realm         | string           | Your domain name for the Generic Onboarding systems account                                                                                        |
| status        | string           | Status of the merchant, initially "new"                                                                                                            |
| backopsUserId | string           | Id of backops user assigned to merchant                                                                                                            |
| landingPage   | array of objects | All the pages and their details of a flow                                                                                                          |
{% endtab %}
{% endtabs %}
