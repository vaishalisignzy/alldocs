# Get Wayne Investor ID

You can check and fetch the Wayne Investor ID (WID) for a particular PAN number, mobile number, or email ID. If the WID already exists in the RTA system, you can directly proceed to creating a folio and skip the step of creating an Investor.

{% swagger method="get" path="/get_wid" baseUrl="https://<<BASE URL>>/investor" summary="Fetch the WID for a PAN number, email ID, or a mobile number." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="pan_number" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobile_number" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="email_id" type="String" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "wid": "********************",
    "panNumber": "",
    "mobileNumber": "",
    "emailId": ""
}
```
{% endswagger-response %}
{% endswagger %}
