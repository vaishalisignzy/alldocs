# Update Related To PEP Details

Looking to update the Investor's related to PEP details in the folios? You can use the below set of API endpoints to execute this and update the related to PEP details.

## Get Related To PEP Details

{% swagger method="get" path="/get_related_to_pep_details" baseUrl="https://<<BASE URL>>/service_requests" summary="Get the related to PEP details associated with the folio of the Investor." %}
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
            "relatedToPep": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        },
        {
            "folioNumber": "",
            "relatedToPep": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        },
        {
            "folioNumber": "",
            "relatedToPep": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        },
        {
            "folioNumber": "",
            "relatedToPep": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        },
        {
            "folioNumber": "",
            "relatedToPep": "",
            "amcName": "",
            "amcCode": "",
            "investorName": ""
        }
    ]
}
```
{% endswagger-response %}
{% endswagger %}

## Update Related To PEP Details

{% swagger method="post" path="/update_related_to_pep_details" baseUrl="https://<<BASE URL>>/service_requests" summary="Update the related to PEP details in a folio of the Investor." %}
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

{% swagger-parameter in="body" name="related_to_pep" type="Boolean" required="true" %}
New value of related to PEP which needs to be updated
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "status": "success",
    "message": "Related to PEP details have been successfully updated in the folio",
    "panNumber": "",
    "wid": "",
    "folioNumber": "",
    "relatedToPepOldValue": "",
    "relatedToPepNewValue": ""
}
```
{% endswagger-response %}
{% endswagger %}
