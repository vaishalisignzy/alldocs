# Change Default Bank Account

You can update or change the default bank account using this API endpoint.

## Get Default Bank Account Details

{% swagger method="get" path="/get_default_bank_account_details" baseUrl="https://<<BASE URL>>/service_requests" summary="Get the default bank account details associated with the folio of the Investor." %}
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
            "amcName": "",
            "amcCode": "",
            "investorName": "",
            "defaultBankAccount": {
                "bankAccountNumber": "",
                "ifscCode": "",
                "bankAccountName": ""
            }
        },
        {
            "folioNumber": "",
            "amcName": "",
            "amcCode": "",
            "investorName": "",
            "defaultBankAccount": {
                "bankAccountNumber": "",
                "ifscCode": "",
                "bankAccountName": ""
            }
        },
        {
            "folioNumber": "",
            "amcName": "",
            "amcCode": "",
            "investorName": "",
            "defaultBankAccount": {
                "bankAccountNumber": "",
                "ifscCode": "",
                "bankAccountName": ""
            }
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

## Change Default Bank Account Details

{% swagger method="post" path="/change_default_bank_account_details" baseUrl="https://<<BASE URL>>/service_requests" summary="Change the bank account details in a folio of the Investor." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="pan_number" type="String" required="true" %}
PAN number of the Investor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="wid" type="String" %}
Wayne Investor ID of the Investor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="folio_number" type="String" required="true" %}
Folio Number of the Investor in which FATCA details is required to be updated
{% endswagger-parameter %}

{% swagger-parameter in="body" name="bank_account_detailss" type="Object" required="true" %}
New value of default bank account details which needs to be updated
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "status": "success",
    "message": "Default bank account details have been successfully updated in the folio",
    "panNumber": "",
    "wid": "",
    "folioNumber": "",
    "defaultBankAccountOldValue": {},
    "defaultBankAccountNewValue": {}
}
```
{% endswagger-response %}
{% endswagger %}
