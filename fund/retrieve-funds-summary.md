# Retrieve Funds Summary

Are you looking to get a summary about the funds details? You can use the below API endpoint for fetching the details about the funds.

{% swagger method="get" path="/funds_summary" baseUrl="https://<<BASE URL>>/fund" summary="Get the summary of all of AMC's funds." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="amc_code" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "amcName": "",
    "asOnDate": "",
    "totalAumSize": "",
    "numberOfFunds": "",
    "averageAumSize": "",
    "totalNumberOfFolios": "",
    "totalUniqueInvestors": "",
    "toalNumberOfNonZeroFolios": "",
    "percentageOfNonZeroFolios": "",
    "fundsSummary": [
        {
            "schemeName": "",
            "schemeCode": "",
            "uniqueInvestors": "",
            "totalFolios": "",
            "totalNonZeroFolios": "",
            "percentageOfNonZeroFolios": ""
        },
        {
            "schemeName": "",
            "schemeCode": "",
            "uniqueInvestors": "",
            "totalFolios": "",
            "totalNonZeroFolios": "",
            "percentageOfNonZeroFolios": ""
        },
        {
            "schemeName": "",
            "schemeCode": "",
            "uniqueInvestors": "",
            "totalFolios": "",
            "totalNonZeroFolios": "",
            "percentageOfNonZeroFolios": ""
        },
        {
            "schemeName": "",
            "schemeCode": "",
            "uniqueInvestors": "",
            "totalFolios": "",
            "totalNonZeroFolios": "",
            "percentageOfNonZeroFolios": ""
        },
        {
            "schemeName": "",
            "schemeCode": "",
            "uniqueInvestors": "",
            "totalFolios": "",
            "totalNonZeroFolios": "",
            "percentageOfNonZeroFolios": ""
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}
