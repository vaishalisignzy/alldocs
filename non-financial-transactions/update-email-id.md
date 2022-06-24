# Update Email ID

Looking to update the Investor's email IDs in the folios? You can use the below set of API endpoints to execute this and update the email ID of the Investor.

## Get Current Email IDs Linked With Folios Details

{% swagger method="get" path="/get_current_email" baseUrl="https://<<BASE URL>>/service_requests" summary="Get the list of current email ID linked with each of the folio numbers." %}
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
            "emailID": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        },
        {
            "folioNumber": "",
            "email ID": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        },
        {
            "folioNumber": "",
            "email ID": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        },
        {
            "folioNumber": "",
            "email ID": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        },
        {
            "folioNumber": "",
            "email ID": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

## Verify New Email ID

You can verify the new email ID given by the Investor, before proceeding with updating the email ID   in the RTA database.

### Generate Email OTP

{% swagger method="post" path="/verify_new_email/generate_email_otp" baseUrl="https://<<BASE URL>>/service_requests" summary="Generate an OTP to be delivered on the email ID." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="email_id" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "status": "success",
    "message": "OTP has been successfully sent to Email ID"
}
```
{% endswagger-response %}
{% endswagger %}

### Verify Email OTP

{% swagger method="post" path="/verify_new_email/verify_email_otp" baseUrl="https://<<BASE URL>>/service_requests" summary="Verify the OTP sent on the email ID using this API endpoint." %}
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

## Update Email ID

{% swagger method="post" path="/update_email" baseUrl="https://<<BASE URL>>/service_requests" summary="Update the email IDs" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="new_email_id" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="wayne_reference_id" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="folio_number" type="Array" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "status": "success",
    "message": "Email ID has been successfully updated in the folios",
    "updatedDetails": [
        {
            "folioNumber": "",
            "amcName": "",
            "previousEmailId": "",
            "UpdatedEmailId": "",
        },
        {
            "folioNumber": "",
            "amcName": "",
            "previousEmailId": "",
            "UpdatedEmailId": "",
        },
        {
            "folioNumber": "",
            "amcName": "",
            "previousEmailId": "",
            "UpdatedEmailId": "",
        }
    ],
    "wayneReferenceId": ""
}
```
{% endswagger-response %}
{% endswagger %}

## Send Confirmation Email

Once the email has been updated, you can automatically send a confirmation email to the Investor using this API endpoint.

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

Once the email has been updated, you can automatically send a confirmation SMS to the Investor using this API endpoint.

{% swagger method="post" path="/send_confirmation_sms" baseUrl="https://<<BASE URL>>/service_requests" summary="Send a confirmation SMS for the changes done in the folio of the Investor." %}
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
    "message": "A confirmation SMS has been sent successfully"
}
```
{% endswagger-response %}
{% endswagger %}
