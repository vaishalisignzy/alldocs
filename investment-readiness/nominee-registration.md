# Nominee Registration

## Why is nominee registration required?

In case the Investor passes away due to any reason, it is much easier to transfer the funds lying in the account of the Investor to the nominee, if it was registered. The nominee can be any individual the Investor trusts and wants the funds to be transferred to in case the Investor passes away due to any unforeseen circumstances. The nominee can be the parents, spouse, siblings, friends, family members, and any other individual the Investor knows and trusts.&#x20;

## Add Nominee

{% swagger method="post" path="/add_nominee" baseUrl="https://<<BASE URL>>/investment_readiness" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="nominee_name" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="nominee_email_id" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="nominee_mobile_number" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="relationship_with_nominee" type="Enums" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="nominee_date_of_birth" type="Date" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="percentage_ownership" type="Double" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" %}

{% endswagger-parameter %}

{% swagger-response status="201: Created" description="Success" %}
```javascript
{
    "status": "success",
    "message": "Nominee has been successfully added"
    "wayneReferenceId": "*******************"
}
```
{% endswagger-response %}
{% endswagger %}
