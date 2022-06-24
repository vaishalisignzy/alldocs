# Daily NAV

You can get the NAV for that particular day for each of the funds.

{% swagger method="get" path="/daily_nav" baseUrl="https://<<BASE URL>>/fund_details" summary="Get the daily NAV of a fund through this API endpoint." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="amc_name" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="scheme_code" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "fund": {
        "amc_name": "",
        "scheme code": "",
        "scheme name": "",
        "scheme type": ""
    },
    "navDetails": {
        "date": "",
        "nav": ""
    }
}
```
{% endswagger-response %}
{% endswagger %}
