# Add a Fund

Launching a new fund offering (NFO)? You can add the fund details of the new fund in RTA system using the following API endpoint.

{% swagger method="post" path="/add_new_fund" baseUrl="https://<<BASE URL>>/fund" summary="Add a NFO details in the RTA system with the below API endpoint." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="fund_name" type="String" required="true" %}
name of the fund
{% endswagger-parameter %}

{% swagger-parameter in="body" name="amc_name" type="String" required="true" %}
name of the amc to which the fund belongs
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fund_category" type="Enums" required="true" %}
category of the fund
{% endswagger-parameter %}

{% swagger-parameter in="body" name="theme" type="Enums" required="true" %}
theme of the fund
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fund_manager" type="Array of objects" required="true" %}
manager of the fund
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fund_type" type="Enums" required="true" %}
type of the fund
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fund_size" type="String" %}
size of the fund
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cash_holdings" type="Number" %}
cash holding of the fund
{% endswagger-parameter %}

{% swagger-parameter in="body" name="plan" type="Enums" required="true" %}
plan of the fund
{% endswagger-parameter %}

{% swagger-parameter in="body" name="expense_ratio" type="Number" required="true" %}
expense ratio of the fund
{% endswagger-parameter %}

{% swagger-parameter in="body" name="exit_load" type="String" required="false" %}
exit load of the fund
{% endswagger-parameter %}

{% swagger-parameter in="body" name="lock_in_period" type="String" %}
lock in period of the fund
{% endswagger-parameter %}

{% swagger-parameter in="body" name="risk_category" type="Enums" required="true" %}
risk category of the fund
{% endswagger-parameter %}

{% swagger-parameter in="body" name="scheme_benchmark" type="String" required="true" %}
benchmark of the fund
{% endswagger-parameter %}

{% swagger-parameter in="body" name="scheme_documents" type="File" required="true" %}
complete scheme document submitted to SEBII
{% endswagger-parameter %}

{% swagger-parameter in="body" name="amc_information" type="Object" required="true" %}
information about the amc
{% endswagger-parameter %}

{% swagger-parameter in="body" name="contact_details" type="String" required="true" %}
contact details
{% endswagger-parameter %}

{% swagger-parameter in="body" name="scheme_start_date" type="Date" required="true" %}
scheme start date
{% endswagger-parameter %}

{% swagger-response status="201: Created" description="Success" %}
```javascript
{
    "status": "success",
    "message": "NFO added succesfully in RTA system",
    "wayneReferenceId": "**************",
    "dateOfAdding": "*****************"
}
```
{% endswagger-response %}
{% endswagger %}
