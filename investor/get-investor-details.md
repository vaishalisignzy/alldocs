# Get Investor Details

You can get to know the details of an Investor for a particular PAN number, email ID or mobile number.

{% swagger method="get" path="/get_investor_details" baseUrl="https://<<BASE URL>>/investor" summary="Get the entire details of an Investor." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="pan_number" type="String" required="true" %}
PAN number of the Investor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobile_number" type="String" %}
Mobile number of the Investor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email_id" type="String" %}
Email ID of the Investor
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "wid": "",
    "panNumber": "",
    "emailID": "",
    "mobileNumber": "",
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
