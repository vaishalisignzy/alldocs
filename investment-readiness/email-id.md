# Email ID

You will use Email ID to communicate with the Investor. You will be sending details about transaction status, investment and redemption status, account statements, service requests, and others.

## Generate Email OTP

You can generate and send an OTP on the registered email ID of the Investor. You can verify the email ID of the Investor using OTP-based verification. The Investor would receive an email with the OTP.

{% swagger method="post" path="/generate_email_otp" baseUrl="https://<<BASE URL>>/investment_readiness" summary="Generate and send an OTP on the registered email ID of the Investor." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="email_id" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "status": "success",
    "message": "OTP has been sent successfully on the email ID"
}
```
{% endswagger-response %}
{% endswagger %}

## Verify Email ID With OTP

{% swagger method="post" path="/verify_email" baseUrl="https://<<BASE URL>>/investment_readiness" summary="Verify the email ID of the Investor with OTP-based verification. " %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="otp" type="Number" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "status": "success",
    "message": "Email ID has been verified successfully",
    "wayneReferenceId": "***********"
}
```
{% endswagger-response %}
{% endswagger %}
