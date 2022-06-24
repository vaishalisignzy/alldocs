# Update Indian Tax Resident Details

Looking to update the Investor's Indian Tax Resident details in the folios? You can use the below set of API endpoints to execute this.

## Get Indian Tax Resident Details

{% swagger method="get" path="/get_indian_tax_resident_details" baseUrl="https://<<BASE URL>>/service_requests" summary="Get the Indian tax resident details associated with the folio of the Investor." %}
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
            "indianTaxResident": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        },
        {
            "folioNumber": "",
            "indianTaxResident": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        },
        {
            "folioNumber": "",
            "indianTaxResident": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        },
        {
            "folioNumber": "",
            "indianTaxResident": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        },
        {
            "folioNumber": "",
            "indianTaxResident": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

## Update Indian Tax Resident Details

{% swagger method="post" path="/update_indian_tax_resident_details" baseUrl="https://<<BASE URL>>/service_requests" summary="Update the Indian tax resident details in a folio of the Investor." %}
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

{% swagger-parameter in="body" name="indian_tax_residentt" type="Boolean" required="true" %}
New value of Indian Tax Resident which needs to be updated
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "status": "success",
    "message": "Indian tax resident details have been successfully updated in the folio",
    "panNumber": "",
    "wid": "",
    "folioNumber": "",
    "indianTaxResidentOldValue": "",
    "indianTaxResidentNewValue": ""
}
```
{% endswagger-response %}
{% endswagger %}
