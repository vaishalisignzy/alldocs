# Mobile Number

You will use mobile number to communicate with the Investor. You will be sending details about transaction status, investment and redemption status, account statements, service requests, and others.

## Generate Mobile OTP

{% swagger method="post" path="/generate_mobile_otp" baseUrl="https://<<BASE URL>>/investment_readiness" summary="Generate and send OTP on the registered mobile number of the Investor for OTP-based verification." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="mobile_number" type="Number" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "status": "success",
    "message": "OTP has been sent successfully on the mobile number"
}
```
{% endswagger-response %}
{% endswagger %}

## Verify Mobile Number With OTP

{% swagger method="post" path="/verify_mobile_number" baseUrl="https://<<BASE URL>>/investment_readiness" summary="Verify the mobile number of the Investor using the OTP generated in the previous step." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="otp" type="Number" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "status": "success",
    "message": "Mobile number has been verified successfully",
    "wayneReferenceId": "**********"
}
```
{% endswagger-response %}
{% endswagger %}
