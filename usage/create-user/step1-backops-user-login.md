# Step1  : Backops User Login

{% swagger baseUrl="https://go-preproduction.signzy.app" path="/api/backopsusers/login" method="post" summary="Backops Login" %}
{% swagger-description %}
Login method for the backops user
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
    "id": "..id..",
    "ttl": "..ttl..",
    "created": "..created..",
    "userId": "..userId..",
    "data": {
        "username": "..username..",
        "applicationId": "..applicationId..",
        "realm": "..realm..",
        "mobile": "..mobile..",
        "lowestLevel": "..lowestLevel..",
        "theme": {
            "_id": ".._id..",
            "name": "..name..",
            "logoUrl": "..logoUrl..",
            "data": {
                "header": "..header..",
                "button": "..button..",
                "highlight": "..highlight..",
                "background": "..background..",
                "cardBackground": "..cardBackground..",
                "headerText": "..headerText..",
                "name": "..name..",
                "sideNavText": "..sideNavText..",
                "buttonText": "..buttonText..",
                "cardBorder": "..cardBorder..",
                "sideNav": "..sideNav..",
                "font": "..font.."
            },
            "applicationId": "..applicationId..",
            "type": "..type.."
        },
        "grantData": {
            "title": "..title..",
            "level": "..level..",
            "grants": "..grants.."
        }
    },
    "isManager": "..isManager.."
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
    "id": "..id..",
    "ttl": "..ttl..",
    "created": "..created..",
    "userId": "..userId..",
    "data": {
        "username": "..username..",
        "applicationId": "..applicationId..",
        "realm": "..realm..",
        "mobile": "..mobile..",
        "lowestLevel": "..lowestLevel..",
        "theme": {
            "_id": ".._id..",
            "name": "..name..",
            "logoUrl": "..logoUrl..",
            "data": {
                "header": "..header..",
                "button": "..button..",
                "highlight": "..highlight..",
                "background": "..background..",
                "cardBackground": "..cardBackground..",
                "headerText": "..headerText..",
                "name": "..name..",
                "sideNavText": "..sideNavText..",
                "buttonText": "..buttonText..",
                "cardBorder": "..cardBorder..",
                "sideNav": "..sideNav..",
                "font": "..font.."
            },
            "applicationId": "..applicationId..",
            "type": "..type.."
        },
        "grantData": {
            "title": "..title..",
            "level": "..level..",
            "grants": "..grants.."
        }
    },
    "isManager": "..isManager.."
}
```

#### Response Field Descriptions

| Key           | Type                             | Description                                                                                                                                        |
| ------------- | -------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| id            | string                           | This is your access token to be passed into other endpoints as Authorization header                                                                |
| ttl           | number                           | <p><strong>Time to live</strong> for your token, which means</p><p>for how much time this token will be valid from the time of </p><p>creation</p> |
| created       | string                           | Time and Date of creation of access-token                                                                                                          |
| userId        | string                           | ID of the backops user                                                                                                                             |
| data          | object                           | Contains the meta-data about the backops                                                                                                           |
| username      | string                           | Username of the backops user                                                                                                                       |
| mobile        | string                           | Mobile number of backops user                                                                                                                      |
| applicationId | string                           | This is the Id to be passed in Pull All Data API, identifier for the application                                                                   |
| realm         | string                           | Your domain name for the Generic Onboarding systems account                                                                                        |
| lowestLevel   | <p>boolean </p><p>(optional)</p> | Tells if its lowest level in hierarchy                                                                                                             |
| theme         | object                           | Contains theme properties of the backops                                                                                                           |
| grantData     | object                           | This tells about the controls allowed to a user                                                                                                    |
| isManager     | boolean                          | Tells if the current backops user is a manager                                                                                                     |
{% endtab %}
{% endtabs %}
