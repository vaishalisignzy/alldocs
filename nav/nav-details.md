# NAV Details

NAV stands for Net assets value. You will get the NAV of a fund over a specified period of time using the below API.

{% swagger method="get" path="/nav_details" baseUrl="https://<<BASE URL>>/fund_details" summary="Get the NAV of a fund over a specified period of time." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="amc_name" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="scheme_code" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="from_date" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="to_date" type="String" required="true" %}

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
    "navDetails": [
        {
            "date": "",
            "nav": ""
        },
        {
            "date": "",
            "nav": ""
        },
        {
            "date": "",
            "nav": ""
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}
