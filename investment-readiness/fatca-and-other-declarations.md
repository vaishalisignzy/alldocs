# FATCA & Other Declarations

## FATCA Declaration

FATCA stands for Foreign Account Tax Compliance Act. It's an act in USA. According to this act, all financial institutions across the world need to report financial transactions of citizens of USA to relevant tax authorities. You can collect the FATCA declaration from the Investor using our APIs.

## Indian Citizens Declaration

You will be able to allow investments from Indian citizens only. You can collect a declaration from the Investor about the status of Indian citizenship.

## Indian Tax Resident Declaration

You will be able to allow investments from Indian tax residents only. You can collect a declaration from the Investor about the status of Indian tax residency.

## Politically Exposed Persons Declaration

PEPs are individuals who are holding prominent positions in public service. For example, officials of political parties, senior army officers, senior judges, senior politicians, senior officials of government owned organizations and companies, and others. If you are going to accept investments from PEPs or individuals who are related with PEPs, in such cases, you would require to do EDD (Enhanced Due Diligence). You would collect additional information and verify them. It may also require prior approvals from concerned organizations.

You will be able to allow investments from non-PEPs individuals only. You can collect a declaration from the Investor about the status of PEPs and related to PEPs.

## Collect FATCA & Other Declarations

{% swagger method="post" path="/fatca_and_other_declarations" baseUrl="https://<<BASE URL>>/investment_readiness" summary="Collect FATCA and other declarations from the Investor." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="fatca" type="Boolean" required="true" %}
FATCA 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="indian_citizen" type="Boolean" required="true" %}
Indian Citizen
{% endswagger-parameter %}

{% swagger-parameter in="body" name="indian_tax_resident" type="Boolean" required="true" %}
Indian Tax Resident Status
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pep" type="Boolean" required="true" %}
Politically Exposed Person Status
{% endswagger-parameter %}

{% swagger-parameter in="body" name="related_to_pep" type="Boolean" required="true" %}
Related To Politically Exposed Person Status
{% endswagger-parameter %}

{% swagger-response status="201: Created" description="Success" %}
```javascript
{
    "status": "success",
    "message": "FATAC & other declarations have been successfully saved",
    "wayneReferenceId": "************"
}
```
{% endswagger-response %}
{% endswagger %}

