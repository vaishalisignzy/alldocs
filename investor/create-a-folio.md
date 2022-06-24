# Create a Folio

Once you have successfully created an Investor ID, you can start creating a Folio. An Investor can have multiple Folios. A Folio stores the investment details of a particular AMC. While creating a folio, you need to collect the investment readiness status from the Investor.&#x20;

{% swagger method="post" path="/create_folio" baseUrl="https://<<BASE URL>>/investor" summary="Create a Folio for an Investor using this API endpoint." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="pan_number" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="wid" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="amc_code" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="ria_code" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="distributor_code" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="scheme_code" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobile_number" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="email_id" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="fatca" type="Boolean" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="indian_citizen" type="Boolean" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="indian_tax_residet" type="Boolean" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="pep" type="Boolean" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="related_to_pep" type="Boolean" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="signature" type="File" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="nominee" type="Array" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="bank_account" type="Object" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="investment_readiness_status" type="Enums" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="wayneReferenceId" type="String" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="201: Created" description="Success" %}
```javascript
{
    "status": "success",
    "message": "Folio successfully created",
    "wayneReferenceID": "",
    "folioNumber": "",
    "creationDateTime": "",
    "creationDate": "",
    "schemeCode": "",
    "schemeName": "",
    "amcName": "",
    "amcCode": ""
}
```
{% endswagger-response %}
{% endswagger %}
