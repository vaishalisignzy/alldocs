# Get Fund Code

Once you have added a new fund details to the RTA system, you can get a scheme code allotted to that particular NFO. The scheme code is the unique numeric identifier of a fund in the RTA system.

{% swagger method="post" path="/scheme_code_allotment" baseUrl="https://<<BASE URL>>/fund" summary="Get a scheme code allotted for a newly added NFO in the RTA system." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="wayne_reference_id" type="String" required="true" %}
Wayne reference Id for addition of the new NFO
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fund_name" type="String" required="true" %}
name of the fund
{% endswagger-parameter %}

{% swagger-parameter in="body" name="amc_name" type="String" required="true" %}
name of the AMC
{% endswagger-parameter %}

{% swagger-parameter in="body" name="date_of_adding" %}
date of adding the fund
{% endswagger-parameter %}

{% swagger-response status="201: Created" description="Success" %}
```javascript
{
    "status": "success",
    "message": "Scheme code allotted successfully",
    "schemeName": "",
    "amcName": "",
    "wayneReferenceId": "",
    "schemeCode": ""
}
```
{% endswagger-response %}
{% endswagger %}

Post you have generated and received the scheme code of a newly added NFO, this new fund can be used for buing, selling, allotment of units to the investors, etc.&#x20;
