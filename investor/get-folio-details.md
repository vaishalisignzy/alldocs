# Get Folio Details

You can get the folio details of an Investor using the below API endpoint.

{% swagger method="get" path="/get_folio_details" baseUrl="https://<<BASE URL>>/investor" summary="Get the folio details of an Investor" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="pan_number" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="wid" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobile_number" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="email_id" type="String" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "wid": "",
    "panNumber": "",
    "folioDetails": [
        {
            "folioNumber": "",
            "amcName": "",
            "amcCode": "",
            "schemeName": "",
            "schemeCode": "",
            "creationDate": "",
            "panNumber": "",
            "mobileNumber": "",
            "emailId": "",
            "kycStatus": "",
            "panStatus": "",
            "defaultBankAccount": {
                "bankAccountNumber": "",
                "ifscCode": "",
                "bankName": "",
                "branchName": "",
                "dateOfAddition": ""
            }
        },
        {
            "folioNumber": "",
            "amcName": "",
            "amcCode": "",
            "schemeName": "",
            "schemeCode": "",
            "creationDate": "",
            "panNumber": "",
            "mobileNumber": "",
            "emailId": "",
            "kycStatus": "",
            "panStatus": "",
            "defaultBankAccount": {
                "bankAccountNumber": "",
                "ifscCode": "",
                "bankName": "",
                "branchName": "",
                "dateOfAddition": ""
            }
        },
        {
            "folioNumber": "",
            "amcName": "",
            "amcCode": "",
            "schemeName": "",
            "schemeCode": "",
            "creationDate": "",
            "panNumber": "",
            "mobileNumber": "",
            "emailId": "",
            "kycStatus": "",
            "panStatus": "",
            "defaultBankAccount": {
                "bankAccountNumber": "",
                "ifscCode": "",
                "bankName": "",
                "branchName": "",
                "dateOfAddition": ""
            }
        },
        {
            "folioNumber": "",
            "amcName": "",
            "amcCode": "",
            "schemeName": "",
            "schemeCode": "",
            "creationDate": "",
            "panNumber": "",
            "mobileNumber": "",
            "emailId": "",
            "kycStatus": "",
            "panStatus": "",
            "defaultBankAccount": {
                "bankAccountNumber": "",
                "ifscCode": "",
                "bankName": "",
                "branchName": "",
                "dateOfAddition": ""
            }
        },
        {
            "folioNumber": "",
            "amcName": "",
            "amcCode": "",
            "schemeName": "",
            "schemeCode": "",
            "creationDate": "",
            "panNumber": "",
            "mobileNumber": "",
            "emailId": "",
            "kycStatus": "",
            "panStatus": "",
            "defaultBankAccount": {
                "bankAccountNumber": "",
                "ifscCode": "",
                "bankName": "",
                "branchName": "",
                "dateOfAddition": ""
            }
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}
