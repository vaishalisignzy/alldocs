# Retrieve Fund Holdings

Are you looking to know about the sector and company wise holdings of a particular fund? You can use the below API to get the information about scheme holdings.

{% swagger method="get" path="/fund_holdings" baseUrl="https://<<BASE URL>>/fund" summary="Get the information about the holdings of a particular fund using this API endpoint." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="fund_code" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "schemeCode": "",
    "schemeName": "",
    "amcName": "",
    "asOnDate": "",
    "companiesHoldings": [
        {
            "companyName": "",
            "companyHoldingsPercentage": "",
            "sector": ""
        },
        {
            "companyName": "",
            "companyHoldingsPercentage": "",
            "sector": ""
        },
        {
            "companyName": "",
            "companyHoldingsPercentage": "",
            "sector": ""
        }
    ],
    "companiesHoldingsSummary": {
        "totalNumberOfCompanies": "",
        "totalHoldingsPercentage": "",
        "topThreeTotalHoldingsPecentage": "",
        "topFiveTotalHoldingsPercentage": ""
    },
    "sectorsHoldings": [
        {
            "sectorName": "",
            "numberOfCompanies": "",
            "sectorHoldingsPercentage": ""
        },
        {
            "sectorName": "",
            "numberOfCompanies": "",
            "sectorHoldingsPercentage": ""
        },
        {
            "sectorName": "",
            "numberOfCompanies": "",
            "sectorHoldingsPercentage": ""
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}
