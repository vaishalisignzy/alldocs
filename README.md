# Authentication

If you are seeing this page, you already have a **username** and an **API key**. The key also acts like your password to the APIs. You need to have an access token for making any further API calls, which you can receive by logging in manually or programmatically using these credentials.

Signzy APIs adhere to authentication defined by **Swagger 2.0** specifications. Each call to the APIs should include an **'Authorization'** header or **'access\_token'** query parameter for authentication.

{% swagger baseUrl="https://signzy.tech" path="/api/v2/patrons/login" method="post" summary="Login" %}
{% swagger-description %}
To access any of the Signzy APIs, you first need to login by making a simple HTTP call.
{% endswagger-description %}

{% swagger-parameter in="body" name="username" type="string" %}
Username
{% endswagger-parameter %}

{% swagger-parameter in="body" name="password" type="string" %}
Password
{% endswagger-parameter %}

{% swagger-response status="200" description="Login successful" %}
```javascript
{
    "id": "...accessToken...",
    "ttl": ..ttl..,
    "created": "..created..",
    "userId": "..patronId..."
  }
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="Request Parameters" %}
| Request Parameter | Type   | Description |
| ----------------- | ------ | ----------- |
| username          | string | username    |
| password          | string | password    |
{% endtab %}

{% tab title="Response Parameters" %}
| Response Parameter | Type     | Description                                           |
| ------------------ | -------- | ----------------------------------------------------- |
| id                 | string   | access token for accessing Signzy APIs                |
| ttl                | integer  | number of seconds for which the access token is valid |
| created            | datetime | timestamp when access token is created                |
| userId             | string   | your userId as on file                                |
{% endtab %}
{% endtabs %}

#### Sending Authenticated Requests

Once you have an access token from the login API call, you can send further calls to different endpoints by passing the access-token in Authorization header or in access\_token query (GET) parameter.

It is advisable to send Access Token in header since, query parameters are sometimes saved in the log files thereby exposing vulnerabilities until the access\_token is deleted from sessions.

#### Security

Anybody with your API key/password or an Access Token generated using them can access all information you have created and also send requests on your behalf. It is strongly recommended to not send API-key/Password to client side and instead use reverse proxy to call Signzy APIs.

If case you think an access token is compromised, you should delete it using logout. Let us know if your Signzy Password/API-key is compromised as soon as possible, so that we can disable & create new ones and prevent any misuse of your data.



{% swagger baseUrl="https://signzy.tech/" path="api/v2/patrons/logout?access_token='access_token'" method="post" summary="Logout" %}
{% swagger-description %}
This method is used to Logout from the Signzy APIs
{% endswagger-description %}

{% swagger-parameter in="query" name="access_token" type="string" %}
access_token - this is basically the 'id' parameter of the response received from the Login request
{% endswagger-parameter %}

{% swagger-response status="204" description="" %}
```
Response code 204 indicates that the access_token has been deleted
```
{% endswagger-response %}
{% endswagger %}
