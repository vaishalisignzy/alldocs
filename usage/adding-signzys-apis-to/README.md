# Editing APIs within the Checks System

{% swagger baseUrl="https://go-preproduction.signzy.app" path="/api/checks/apiMapping" method="put" summary="Edit API" %}
{% swagger-description %}
This API allows you to edit an API within the Checks System which will execute when the Merchant's journey is completed, and the proper conditions for executing the API are met.

\


The required `apiId` and `type` parameters can be fetched using `/integration/apispecifications` from the same base URL as above.

\


This is required since if a Check is already defined, there is no way to edit the API input mapping.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
Authorization Token generated from application login or dashboard user login.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="apiId" type="string" %}
ID of the API being called.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="type" type="string" %}
Type of the API being called.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mapping" type="object" %}
Input mapping of data required as input parameters for Signzy's API.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="flowId" type="string" %}
ssigned, to trigger the API.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pageId" type="string" %}
ID of the page which when used in conjunction with widgetNames gives unique data to operate on.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="widgetName" type="string" %}
Name of the widget which when used by the Merchant should trigger the API to be run.
{% endswagger-parameter %}

{% swagger-response status="200" description="API successfully configured." %}
```
{ "result": "ok" }
```
{% endswagger-response %}

{% swagger-response status="400" description="Something in the request is missing or invalid." %}
```
{
    "error": {
        "statusCode": 400,
        "name": "Error",
        "message": "'dataSource.value' must be specified",
        "details": {}
    }
}

// OR

{
    "error": {
        "statusCode": 400,
        "name": "Error",
        "message": "TypeError: Cannot read property 'level' of undefined",
        "details": {}
    }
}
```
{% endswagger-response %}
{% endswagger %}

