# Update FATCA Details

Looking to update the Investor's FATCA details in the folios? You can use the below set of API endpoints to execute this and update the FATCA details.

## Get FATCA Details

{% swagger method="get" path="/get_fatca_details" baseUrl="https://<<BASE URL>>/service_requests" summary="Get the FATCA details associated with the folio of the Investor." %}
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
            "fatca": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        },
        {
            "folioNumber": "",
            "fatca": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        },
        {
            "folioNumber": "",
            "fatca": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        },
        {
            "folioNumber": "",
            "fatca": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        },
        {
            "folioNumber": "",
            "fatca": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

## Update FATCA Details

{% swagger method="post" path="/update_fatca_details" baseUrl="https://<<BASE URL>>/service_requests" summary="Update the FATCA details in a folio of the Investor." %}
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

{% swagger-parameter in="body" name="fatca" type="Boolean" required="true" %}
New value of FATCA which needs to be updated
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "status": "success",
    "message": "FATCA details have been successfully updated in the folio",
    "panNumber": "",
    "wid": "",
    "folioNumber": "",
    "fatcaOldValue": "",
    "fatcaNewValue": ""
}
```
{% endswagger-response %}
{% endswagger %}
