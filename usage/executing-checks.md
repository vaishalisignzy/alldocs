# Executing Checks

{% swagger baseUrl="https://go-preproduction.signzy.app" path="/api/checks/runChecks/:applicationId/:merchantId" method="post" summary="Run Checks" %}
{% swagger-description %}
This endpoint runs the configured Checks, Decisions, and stores results accordingly to the Merchant's data. This must be called after the Merchant has finished onboarding.
{% endswagger-description %}

{% swagger-parameter in="path" name="applicationId" type="string" %}
Application ID
{% endswagger-parameter %}

{% swagger-parameter in="path" name="merchantId" type="string" %}
ID of Merchant
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
Authorization Token generated from logging in as a Merchant.
{% endswagger-parameter %}

{% swagger-response status="200" description="Checks successfully run." %}
```
{
    "result": {
        "requestId": "requestId"
    }
}
```
{% endswagger-response %}

{% swagger-response status="400" description="Something in the request was missing or invalid." %}
```
{
    "error": {
        "merchantNotFound": true
    }
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://go-preproduction.signzy.app" path="/api/checks/getDEResult/:requestId" method="get" summary="Get processed result by request ID" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="requestId" type="string" %}
Request Id generated after run checks
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "result": {
        "_id": "",
        "status": "complete",
        "input": {
            "data": [
                {
                    "pageId": "",
                    "data": {
                    },
                    "pageName": "Passport",
                    "flowId": "",
                    "pageType": "Data&Document",
                    "isSubflow": false,
                    "applicationId": "",
                    "uid": "",
                    "merchantId": "",
                    "_id": "5fd3576e598e9344d76a91da"
                },
                {
                    "pageId": "",
                    "data": {
                    },
                    "pageName": "Video Match",
                    "flowId": "",
                    "pageType": "Data&Document",
                    "isSubflow": false,
                    "applicationId": "",
                    "uid": "",
                    "merchantId": "",
                    "_id": "5fd3576e598e9344d76a91db"
                }
            ]
        },
        "output": {
            "pageResults": {
                "5fb3a29f8624e77fd9e6ff65": [
                    
                ],
                "5fb3a29f8624e77fd9e6ff65": [
                    
                ]
            },
            "finalResult": {
                "result": "uncertain"
            }
        }
    }
}
```
{% endswagger-response %}
{% endswagger %}

