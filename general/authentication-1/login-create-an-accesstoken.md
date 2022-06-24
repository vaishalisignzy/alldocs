# Login - Create an Access Token

Access Tokens are used in token-based authentication to allow an application to access an API. The application receives an Access Token after a user successfully authenticates and authorizes access, then passes the Access Token as a credential when it calls the target API. The passed token informs the API that the bearer of the token has been authorized to access the API and perform specific actions specified by the scope that was granted during authorization.



{% swagger baseUrl="https://deepfaceauth.signzy.app/deepfaceauth" path="/api/v1/basic/login" method="post" summary="Login-create an access token" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerName" type="string" %}
Customer Name was given to you by Signzy
{% endswagger-parameter %}

{% swagger-parameter in="body" name="password" type="string" %}
Password is given to you by Signzy
{% endswagger-parameter %}

{% swagger-response status="200" description="application/json" %}
```
{
  "accessToken": "...access token...",
  "status": "200 OK",
  "message": "Successfully Logged In"
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="Request Schema" %}
```
{
  "customerName": "...userName given to you by Signzy...",
  "password": "...password given to you by Signzy..."
}
```
{% endtab %}

{% tab title="Response Parameter" %}
| Parameter Name | Parameter Type | Parameter Description                                      |
| -------------- | -------------- | ---------------------------------------------------------- |
| accessToken    | string         | accessToken which you have to pass in authorization header |
| status         | string         | status of the request                                      |
| message        | string         | message to the user                                        |


{% endtab %}
{% endtabs %}

