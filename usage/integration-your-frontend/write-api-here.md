# Backops User Login

{% swagger baseUrl="https://go-preproduction.signzy.app" path="/api/backopsusers/login" method="post" summary="Backops User Login" %}
{% swagger-description %}
This API allows you to pass information about the Backops user and get authentication token from the server. Later this Authentication token will be used in subsequent requests to communicate to Signzy's Backops APIs.
{% endswagger-description %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="body" name="username" type="string" %}
Username of the backops user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="password" type="string" %}
Password for the respective username
{% endswagger-parameter %}

{% swagger-parameter in="body" name="realm" type="string" %}
Domain name in generic on-boarding system
{% endswagger-parameter %}

{% swagger-response status="200" description="Login Successful" %}
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

{% swagger-response status="400" description="Realm not passed. Realm is a required parameter" %}
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

| Key      | Type   | Description                               |
| -------- | ------ | ----------------------------------------- |
| username | string | Username of the backops user              |
| password | string | Password for the respective username      |
| realm    | string | Domain name in generic on-boarding system |
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

| Key                  | Type                            | Description                                                                                                                |
| -------------------- | ------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| id                   | string                          | This is the user access token which will be passed for every subsequent request for this user as the Authorization Header. |
| ttl                  | number                          | **Time to Live** for the token, which means for how much time this token will be valid from the time of creation.          |
| created              | string                          | Time and Date of creation of access-token                                                                                  |
| userId               | string                          | ID of the backops user                                                                                                     |
| **data**             | object                          | Contains the meta-data about the backops.                                                                                  |
| data._username_      | string                          | Username of the backops                                                                                                    |
| data._mobile_        | string                          | Mobile number of backops user                                                                                              |
| data._applicationId_ | string                          | This is the Id to be passed in the Pull All Data API related to the application.                                           |
| data._realm_         | string                          | Your domain name for the on-boarding systems account                                                                       |
| data._lowestLevel_   | <p>boolean</p><p>(optional)</p> | Tells if it's the lowest level in hierarchy                                                                                |
| data._theme_         | object                          | Contains the theme properties of the backops                                                                               |
| data._grantData_     | object                          | This JSON object gives information about the controls allowed to the user.                                                 |
| isManager            | boolean                         | Tells if the current backops user is a manager.                                                                            |
{% endtab %}
{% endtabs %}
