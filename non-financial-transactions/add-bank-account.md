# Add Bank Account

Verify and add the bank account details of an Investor.

## Verify bank account

{% swagger method="post" path="/verify_bank_account" baseUrl="https://<<BASE URL>>/service_requests" summary="Verify the bank account by doing a penny drop transaction automatically." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" type="String" name="ifsc_code" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="beneficiary_account_number" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="bank_account_type" type="Enum" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="beneficiary_name" type="String" required="false" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="beneficiary_mobile_number" type="Number" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="beneficiary_email_id" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="transfer_amount" type="Double" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="message" required="true" type="String" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "status": "success",
    "message": "Bank account number has been successfully verified",
    "beneficiaryAccountNumber": "111111111111",
    "ifscCode": "UTIB0000004",
    "bankName": "Axis Bank",
    "branchName": "Mumbai",
    "beneficiaryName": "",
    "accountStatus": "active",
    "bankAccountType": "Savings/Current"
    "bankReferenceNumber": "",
    "wayneReferenceId": "",
    "timestamp": ""
}
```
{% endswagger-response %}
{% endswagger %}

## Perform beneficiary name text match

{% swagger method="post" path="/beneficiary_name_text_match" baseUrl="https://<<BASE URL>>/service_requests" summary="Perform a text match of the beneficiary name of the bank account number with the KYC name of the Investor." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="kyc_name" required="true" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="beneficiary_name" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "textMatchScore": "",
    "textMatchResult": "Zero Match/Partial Match/Full Match"
}
```
{% endswagger-response %}
{% endswagger %}

The text match score would vary from 0 to 100.

* Zero Match - 0&#x20;
* Partial Match - 1 - 99
* Full Match - 100

### Zero Match Scenarios

In Zero Match scenarios, ask the Investor to provide the bank account details that belongs to them.  As the beneficiary name of the bank account doesn't match with the KYC name of the Investor, the bank account details should not be passed to the next step of adding the bank account.

### Partial Match Scenarios

In Partial Match scenarios, ask the Investor to upload a cancelled cheque copy with the name of the account holder printed on it for verifying it manually.

### Full Match Scenarios

In Full Match scenarios, you can pass the bank account details for addition in the next step.

## Add bank account

{% swagger method="post" path="/add_bank_account" baseUrl="https://<<BASE URL>>/service_requests" summary="With this API, you can add a bank account of an investor." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="ifsc_code" required="true" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="beneficiary_account_number" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="bank_account_type" type="Enum" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="bank_name" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="branch_name" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="beneficiary_name" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="wayne_reference_id" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="cancelled_cheque_copy" type="File" %}

{% endswagger-parameter %}

{% swagger-response status="201: Created" description="Success" %}
```javascript
{
    "status": "success",
    "message": "Bank account has been succesfully added",
    "wayneRefrenceId": ""
}
```
{% endswagger-response %}
{% endswagger %}
