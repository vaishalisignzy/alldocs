# Update a Fund

You can update the following:

* Fund Category
* Theme
* Fund Manager
* Fund Type
* Fund Size
* Cash Holdings
* Plan
* Expense Ratio
* Exit Load
* Lock In Period

Use the following API endpoint to update the fund.

{% swagger method="post" path="/update_a_fund/:fund_code" baseUrl="https://<<BASE URL>>/fund" summary="Update the fund details in the RTA system with the below API endpoint." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="fund_category" type="Enums" required="false" %}
category of the fund
{% endswagger-parameter %}

{% swagger-parameter in="body" name="theme" type="Enums" required="false" %}
theme of the fund
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fund_manager" type="Array of objects" required="false" %}
manager of the fund
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fund_type" type="Enums" required="false" %}
type of the fund
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fund_size" type="String" %}
size of the fund
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cash_holdings" type="Number" %}
cash holding of the fund
{% endswagger-parameter %}

{% swagger-parameter in="body" name="plan" type="Enums" required="false" %}
plan of the fund
{% endswagger-parameter %}

{% swagger-parameter in="body" name="expense_ratio" type="Number" required="false" %}
expense ratio of the fund
{% endswagger-parameter %}

{% swagger-parameter in="body" name="exit_load" type="String" required="false" %}
exit load of the fund
{% endswagger-parameter %}

{% swagger-parameter in="body" name="lock_in_period" type="String" %}
lock in period of the fund
{% endswagger-parameter %}

{% swagger-response status="201: Created" description="Success" %}
```javascript
{
    "status": "success",
    "message": "Fund details updated succesfully in RTA system",
    "wayneReferenceId": "**************"
}
```
{% endswagger-response %}
{% endswagger %}
