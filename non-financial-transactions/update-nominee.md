# Update Nominee

You can update the nominee details using the below API endpoint. You can update the details like changing the percentage of ownership, mobile number of nominee, and so on.

## Get Nominee Details

{% swagger method="get" path="/get_nominee_details" baseUrl="https://<<BASE URL>>/service_requests" summary="Get the nominee details associated with the folio of the Investor." %}
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
            "nomineeDetails": [
                {
                    "nomineeName": "",
                    "nomineeMobileNumber": "",
                    "nomineeEmailId": "",
                    "percenatgeOwnership": ""
                }
            ]
        },
        {
            "folioNumber": "",
            "amcName": "",
            "amcCode": "",
            "investorName": "",
            "nomineeDetails": [
                {
                    "nomineeName": "",
                    "nomineeMobileNumber": "",
                    "nomineeEmailId": "",
                    "percenatgeOwnership": ""
                }
            ]
        },
        {
            "folioNumber": "",
            "amcName": "",
            "amcCode": "",
            "investorName": "",
            "nomineeDetails": [
                {
                    "nomineeName": "",
                    "nomineeMobileNumber": "",
                    "nomineeEmailId": "",
                    "percenatgeOwnership": ""
                }
            ]
        } 
    ]
}
```
{% endswagger-response %}
{% endswagger %}

## Update Nominee Details

{% swagger method="post" path="/update_nominee_details" baseUrl="https://<<BASE URL>>/service_requests" summary="Update the nominee details in a folio of the Investor." %}
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

{% swagger-parameter in="body" name="nominee_details" type="Object" required="true" %}
New value of nominee details which needs to be updated
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "status": "success",
    "message": "Nominee details have been successfully updated in the folio",
    "panNumber": "",
    "wid": "",
    "folioNumber": "",
    "nomineeOldValue": {},
    "nomineeNewValue": {}
}
```
{% endswagger-response %}
{% endswagger %}
