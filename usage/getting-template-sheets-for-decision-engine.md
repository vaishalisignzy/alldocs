# Getting Template Sheets for Decision Engine

{% swagger baseUrl="https://go-preproduction.signzy.app" path="/api/checks/getTemplateSheet" method="post" summary="Get Template Sheet" %}
{% swagger-description %}
This endpoint provides a template sheet in which preferences for making decisions can be fed.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
Authorization Token generated from either application login, or dashboard user login.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="variables" type="array" %}
Array of Objects whose structure is given below.
{% endswagger-parameter %}

{% swagger-response status="200" description="Template Sheet generated." %}
```
{
    "sheet": "<<link to download>>"
}
```
{% endswagger-response %}

{% swagger-response status="400" description="Something within the request is wrong. The response will detail what it is" %}
```
{
    "error": {
        "statusCode": 422,
        "name": "Error",
        "message": "'dataSource.value.type' and 'dataSource.value.data' must be specified",
        "details": {}
    }
}
```
{% endswagger-response %}
{% endswagger %}

### \`variables\` parameter structure

```
[
    {
        "type": "check",
        "data": "<<checkId>>" // Eg. 5dc960656a15482e45664c86
    },
    {
        "type": "api",
        "data": "<<apiOutputParam>>" // Eg. DOBMatchScore
    },
    {
        "type": "pageVariable",
        "data": {
            "pageId": "<<pageId>>", // Eg. 5dc960656a15482e45664c86
            "variable": "<<variableName>>", // Eg. PanNameName
        }
    }
]
```
