# Update Mobile Number

Looking to update the Investor's mobile number in the folios? You can use the below set of API endpoints to execute this and update the mobile number of the Investor.

## Get Current Mobile Number Linked With Folios Details

{% swagger method="get" path="/get_current_mobile_number" baseUrl="https://<<BASE URL>>/service_requests" summary="Get the list of current mobile numbers linked with each of the folio numbers." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="pan_number" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="wid" type="String" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "folioDetails": [
        {
            "folioNumber": "",
            "mobileNumber": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        },
        {
            "folioNumber": "",
            "mobileNumber": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        },
        {
            "folioNumber": "",
            "mobileNumber": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        },
        {
            "folioNumber": "",
            "mobileNumber": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        },
        {
            "folioNumber": "",
            "mobileNumber": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

## Verify New Mobile Number

You can verify the new mobile number given by the Investor, before proceeding with updating the mobile number in the RTA database.

### Generate Mobile OTP

{% swagger method="post" path="/verify_mobile_number/generate_mobile_otp" baseUrl="https://<<BASE URL>>/service_requests" summary="Generate an OTP to be delivered on the mobile number." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="mobile_number" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "status": "success",
    "message": "OTP has been successfully sent to the mobile number"
}
```
{% endswagger-response %}
{% endswagger %}

### Verify OTP

{% swagger method="post" path="/verify_mobile_number/verify_mobile_otp" baseUrl="https://<<BASE URL>>/service_requests" summary="Verify the OTP sent on the mobile number using this API endpoint." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="otp" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "status": "success",
    "message": "OTP has been successfully verified",
    "wayneReferenceId": "**************"
}
```
{% endswagger-response %}
{% endswagger %}

## Update Mobile Number

{% swagger method="post" path="/update_mobile_number" baseUrl="https://<<BASE URL>>/service_requests" summary="Update the mobile numbers." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="new_mobile_number" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="wayne_reference_id" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="folio_numbers" type="Array" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "status": "success",
    "message": "Mobile number has been successfully updated in the folios",
    "updatedDetails": [
        {
            "folioNumber": "",
            "amcName": "",
            "previousMobileNumber": "",
            "UpdatedMobileNumber": "",
        },
        {
            "folioNumber": "",
            "amcName": "",
            "previousMobileNumber": "",
            "UpdatedMobileNumber": "",
        },
        {
            "folioNumber": "",
            "amcName": "",
            "previousMobileNumber": "",
            "UpdatedMobileNumber": "",
        }
    ],
    "wayneReferenceId": ""
}
```
{% endswagger-response %}
{% endswagger %}

## Send Confirmation Email

Once the mobile number has been updated, you can automatically send a confirmation email to the Investor using this API endpoint.

{% swagger method="post" path="/send_confirmation_email" baseUrl="https://<<BASE URL>>/service_requests" summary="Send a confirmation email for the changes done in the folio of the Investor." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="wid" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="wayne_reference_id" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "status": "success",
    "message": "A confirmation email has been successfully sent to the Investor"
    "wayneReferenceId": ""
}
```
{% endswagger-response %}
{% endswagger %}

## Send Confirmation SMS

Once the mobile number has been updated, you can automatically send a confirmation SMS to the Investor using this API endpoint.

{% swagger method="post" path="/send_confirmation_sms" baseUrl="https://<<BASE URL>>/service_requests" summary="Send a confirmation email for the changes done in the folio of the Investor." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="wid" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="wayne_reference_id" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "status": "success",
    "message": "A confirmation sms has been successfully sent to the Investor"
    "wayneReferenceId": ""
}
```
{% endswagger-response %}
{% endswagger %}
