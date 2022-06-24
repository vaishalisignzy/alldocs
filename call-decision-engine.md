# Call Decision Engine with End-User data

{% swagger baseUrl="https://go-preproduction.signzy.app" path="/api/checks/runChecks/:applicationId/:merchantId" method="post" summary="Run Checks" %}
{% swagger-description %}
This endpoint runs the configured Checks, Decisions, and stores results accordingly to the Merchant's data. This must be called after the Merchant has finished onboarding.
{% endswagger-description %}

{% swagger-parameter in="path" name="applicationId" type="string" %}
Application ID returned from backops login request
{% endswagger-parameter %}

{% swagger-parameter in="path" name="merchantId" type="string" %}
Unique Identifier of the Merchant.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
Authorization Token generated from backops user login
{% endswagger-parameter %}

{% swagger-parameter in="body" name="callback" type="string" %}
A callback url to push the proessed data
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mode" type="string" %}
A value "push" must be provided
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data" type="array" %}
An array of objects containing data of each step
{% endswagger-parameter %}

{% swagger-response status="200" description="All checks successfully run." %}
```
{
    "result": {
        "requestId" : "...requestId..." // A unique ID through which DE 
                                            result can be fetched
    }
}
```
{% endswagger-response %}

{% swagger-response status="400" description="Something in the request was missing or invalid." %}
```
{
    "error": {
        "statusCode": 400,
        "name": "Error",
        "message": "'dataSource.value' must be specified",
        "details": {}
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

### Sample request body and field descriptions

{% tabs %}
{% tab title="Request Body" %}
```
{
  "mode": "push",
  "callback": "https://xyz.xyz",
  "data": [
    {
      "pageId": "...pageId1...", //taken from mapping return in merchant login
      "pageName": "...pageName1...", //taken from mapping return in merchant login
      "uid": "...uid...",
      "type": "...type...",
      "widgetName": "...widgetName..."
      "data": {
        "variable1": "...variable1...",
        "variable2": "...variable2...",
        "variable3": "...variable3...",
        "variable4": "...variable4...",
        "variable5": "...variable5...",
        "variable6": "...variable6...",
        "variable7": "...variable7...",
        "document": "...document1...", //harcoded for the step
        "apiName": "...apiName1.." //harcoded for the step
      },
      "pageType": "...pageType...", //taken from mapping return in merchant login
      "isSubflow": false //harcoded for the step
    },
    {
      "pageId": "...pageId2...", //taken from mapping return in merchant login
      "pageName": "...pageName2...", //taken from mapping return in merchant login
      "uid": "...uid...",
      "type": "...type...",
      "widgetName": "...widgetName..."
      "data": {
        "variable8": "...variable8...",
        "variable9": "...variable9...",
        "variable10": "...variable10...",
        "variable11": "...variable11...",
        "variable12": "...variable12...",
        "variable13": "...variable13...",
        "variable14": "...variable14...",
        "variable15": "...variable15...",
        "document": "...document2...", //harcoded for the step
        "apiName": "...apiName2.." //harcoded for the step
      },
      "pageType": "...pageType...", //taken from mapping return in merchant login
      "isSubflow": false //harcoded for the step
    }
  ]
}
```

#### Field Descriptions

| Key                | Type             | Description                                                                              |
| ------------------ | ---------------- | ---------------------------------------------------------------------------------------- |
| data               | Array of objects | Object containing the data of each step                                                  |
| data.pageId        | String           | Page Id of the step, to be taken from landingPage array returned in merchant login       |
| data.pageName      | String           | Page Name of the step, to be taken from landingPage array returned in merchant login     |
| data.uid           | String           | User-Id, will be merchant Id when subflow is false                                       |
| data.data          | Object           | Contains the end user variables and meta-data                                            |
| data.data.document | String           | Document of the data provided, hardcoded, will be provided by Signzy                     |
| data.data.apiName  | String           | API Name for the step, hardcoded, will be provided by Signzy                             |
| data.pageType      | String           | Type of page for the step, to be taken from landingPage array returned in merchant login |
| data.isSubflow     | Boolean          | false, hardcoded, true only when submitting for subflow                                  |
{% endtab %}
{% endtabs %}
