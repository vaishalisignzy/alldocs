# Retrieve a Fund

You can retrieve the fund information by passing the fund id.

{% swagger method="get" path="/:fund_id" baseUrl="https://<<BASE URL>>/fund" summary="Get the fund details with the below API endpoint." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "schemeName": "",
    "schemeCode": "",
    "amcName": "",
    "fundCategory": "",
    "theme": "",
    "fundManager": [
        {
            "fundManagerName": "",
            "totalExperience": "",
            "about": "",
            "aumSize": ""
        },
        {
            "fundManagerName": "",
            "totalExperience": "",
            "about": "",
            "aumSize": ""
        }
    ],
    "fundType": "",
    "schemeSize": "",
    "cashHolding": "",
    "plan": "",
    "expenseRatio": "",
    "exitLoad": "",
    "schemeBenchmark": "",
    "schemeStartDate": "",
    "schemeDocuments": "",
    "amcInformation": {
        "totalAum": "",
        "numberOfSchemes": ""
    },
    "contactDetails": "",
    "riskCategorisation": "",
    "lockInPeriod": ""
}
```
{% endswagger-response %}
{% endswagger %}
