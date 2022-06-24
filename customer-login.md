# Authentication

### Authorising your access

The APIs you have a username and an API key. The key also acts like your password to the APIs. You need to have an access token for making any further API calls, which you can receive by logging in manually or programmatically using these credentials.

Signzy APIs adhere to authentication defined by Swagger 2.0 specifications. Each call to the APIs should include an 'Authorisation' header or 'access\_token' query parameter for authentication. need an authorisation token to utilise the APIs.&#x20;

### Logging In

For using Signzy APIs you have to first Login into Signzy System which is a simple Rest API(HTTPS) call with JSON parameters as username and password. Following section mentions the data to be input, expected output and meaning of fields in JSON.

{% swagger baseUrl="https://video-conf-demo.signzy.app" path="/scheduling/Customers/login" method="post" summary="Customer Login API" %}
{% swagger-description %}
Use login credentials to generate Authentication token
{% endswagger-description %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
VALUE: "application/json"
{% endswagger-parameter %}

{% swagger-parameter in="body" name="username" type="string" %}
Customer's username
{% endswagger-parameter %}

{% swagger-parameter in="body" name="password" type="string" %}
Customer's password
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```javascript
{
    "id": "JGzq4yWXJGF6DouxkiKkEElLfu1DE7mXdOW2XLgjDQTog3Pulb9peRsCpAdT2i8S",
    "ttl": 1209600,
    "created": "2020-03-02T15:21:31.457Z",
    "userId": "5e3b02507ffff2001ad6a81d"
}
```
{% endswagger-response %}
{% endswagger %}
