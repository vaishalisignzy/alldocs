# Update PEP Details

Looking to update the Investor's PEP details in the folios? You can use the below set of API endpoints to execute this and update the PEP details of the Investor.

## Get PEP Details

{% swagger method="get" path="/get_pep_details" baseUrl="https://<<BASE URL>>/service_requests" summary="Get the PEP details associated with the folio of the Investor." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="pan_number" type="String" required="true" %}
PAN number of the Investor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="wid" type="String" %}
Wayne Investor ID of the Investor
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "folioDetails": [
        {
            "folioNumber": "",
            "pep": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        },
        {
            "folioNumber": "",
            "pep": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        },
        {
            "folioNumber": "",
            "pep": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        },
        {
            "folioNumber": "",
            "pep": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        },
        {
            "folioNumber": "",
            "pep": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

## Update PEP Details

{% swagger method="post" path="/update_pep_details" baseUrl="https://<<BASE URL>>/service_requests" summary="Update the PEP details in a folio of the Investor." %}
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

{% swagger-parameter in="body" name="pep" type="Boolean" required="true" %}
New value of PEP which needs to be updated
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "status": "success",
    "message": "PEP details have been successfully updated in the folio",
    "panNumber": "",
    "wid": "",
    "folioNumber": "",
    "pepOldValue": "",
    "pepNewValue": ""
}
```
{% endswagger-response %}
{% endswagger %}
