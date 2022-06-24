# Create an Investor

The first step is to create an investor profile in the RTA system. You can use the below API to create an investor. You will be generating a Wayne Investor ID (WID). This is the unique identifier of an investor in the RTA system. The PAN number, mobile number, and the email ID are uniquely associated with the Wayne Investor ID (WID).&#x20;

{% swagger method="post" path="/create_investor" baseUrl="https://<<BASE URL>>/investor" summary="Create an investor and generate an unique WID." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="kyc_name" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="display_name" type="String" required="false" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="investor_photo" type="File" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="gender" type="Enums" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="date_of_birth" type="Date" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="pan_number" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="aadhaar_number" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobile_number" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="email_id" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="permanent_address" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="communication_address" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="kyc_status" type="Enums" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="pan_status" type="Enums" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="201: Created" description="Success" %}
```javascript
{
    "status": "success",
    "message": "Wayne Investor ID created successfully",
    "wid": "",
    "wayneReferenceId": "",
    "dateTime": ""
}
```
{% endswagger-response %}
{% endswagger %}
