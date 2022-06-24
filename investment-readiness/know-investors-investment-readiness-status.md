# Know Investor's Investment Readiness Status

You can get to know about the investment readiness status of an investor using the below API endpoint.

## Investment Readiness Status

{% swagger method="post" path="/investment_readiness_status" baseUrl="https://<<BASE URL>>/investment_readiness" summary="Get to know the status of investment readiness for an Investor." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" type="String" name="pan_number" required="true" %}
PAN number of the Investor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="date_of_birth" required="true" type="String" %}
Date of birth of the Investor
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "panNumber": "",
    "dob": "",
    "name": "",
    "investmentReadinessStatus": "",
    "investmentReadinessDetails": {
        "emailID": "",
        "mobileNumber": "",
        "fatca": "",
        "signature": "",
        "nomineeDetails": {},
        "bankAccountDetails": {}
    }
}
```
{% endswagger-response %}
{% endswagger %}

##
