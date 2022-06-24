# Systematic Buy

You can buy a Mutual Fund using systematic investment plans and get units and NAV allotted for the investor using the below steps.

1. Create a SIP (systematic investment plan) order
2. Confirmation of payment on each of the SIP dates
3. Units and NAV allotment on each of the SIP dates

## Create a SIP order

{% swagger method="post" path="create_sip_order" baseUrl="https://<<BASE URL>>/financial_transactions/systematic_buy/" summary="Create a SIP buy order for a particular scheme." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="investor_id" type="String" required="true" %}
Unique ID of the investor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="scheme_id" type="String" required="true" %}
ID of the scheme in which Mutual Fund investment is to be done
{% endswagger-parameter %}

{% swagger-parameter in="body" name="amount" type="String" required="true" %}
Amount of money for which the mutual fund is to be purchased
{% endswagger-parameter %}

{% swagger-parameter in="body" name="frequency" type="Enums" required="true" %}
Monthly, Quarterly, Half-Yearly & Yearly
{% endswagger-parameter %}

{% swagger-parameter in="body" name="number_of_installmentss" type="String" %}
Number of installments of the SIP
{% endswagger-parameter %}

{% swagger-parameter in="body" name="start_date" type="String" required="true" %}
Date of starting the SIP
{% endswagger-parameter %}

{% swagger-parameter in="body" name="end_date" type="String" required="true" %}
Date of ending the SIP
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mandate_id" type="String" required="true" %}
Mandate ID for payments
{% endswagger-parameter %}

{% swagger-response status="201: Created" description="Success" %}
```javascript
{
    "investorId": "",
    "schemeId": "",
    "amount": "",
    "dateTime": "",
    "wayneSIPId": "",
    "mandateId": ""
}
```
{% endswagger-response %}
{% endswagger %}

## Confirmation of payment on each of SIP dates

{% swagger method="post" path="payment_confirmation" baseUrl="https://<<BASE URL>>/financial_transactions/systematic_buy/" summary="Get the confirmation status of the payment against each of SIP dates." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="wayne_order_id" type="String" required="true" %}
Order ID of the buy order placed in previous step
{% endswagger-parameter %}

{% swagger-parameter in="body" name="investor_id" type="String" required="true" %}
Unique Id of the Investor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="sip_id" type="String" required="true" %}
SIP Id of the investor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mandate_id" type="String" required="true" %}
Mandate Id of the investor
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "investorId": "",
    "wayneSipId": "",
    "mandateId": "",
    "bankReferenceNumber": "",
    "paymentStatus": "",
    "dateTimeOfAmountCredited": "",
    "amount": ""
}
```
{% endswagger-response %}
{% endswagger %}

## Units & NAV Allotment on each of SIP dates

{% swagger method="post" path="units_nav_allotment" baseUrl="https://<<BASE URL>>/financial_transactions/systematic_buy/" summary="Get the units and NAV allotted against the SIP orders." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="investor_id" type="String" required="true" %}
Unique Id of the investor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="wayne_sip_id" type="String" required="true" %}
SIP ID of the order placed
{% endswagger-parameter %}

{% swagger-parameter in="body" name="bank_reference_number" type="String" required="true" %}
Bank reference number of the amount deposited
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mandate_id" type="String" required="true" %}
Mandate Id of the investor
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "invetsorId": "",
    "schemeName": "",
    "schemeCode": "",
    "amount": "",
    "sipId": "",
    "mandateId": "",
    "navAllotmentDate": "",
    "navAllotted": "",
    "unitsAllotted": ""
}
```
{% endswagger-response %}
{% endswagger %}

## Send confirmation SMS to investor

{% swagger method="post" path="send_confirmation_sms" baseUrl="https://<<BASE URL>>/financial_transactions/systematic_buy/" summary="Send a confirmation SMS to the investor with the Units, NAV and other details for the allotment." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="investor_id" type="String" required="true" %}
Unique Id of the investor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="wayne_sip_id" type="String" required="true" %}
SIP Id of the order placed
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mobile_number" type="String" required="true" %}
Mobile number of the investor
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "wayneReferenceId": "",
    "message": ""
}
```
{% endswagger-response %}
{% endswagger %}

## Send confirmation Email to investor

{% swagger method="post" path="send_confirmation_email" baseUrl="https://<<BASE URL>>/financial_transactions/systematic_buy/" summary="Send a confirmation Email to the investor with the Units, NAV and other details for the allotment." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="investor_id" type="String" required="true" %}
Unique id of the investor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="wayne_sip_id" type="String" required="true" %}
SIP id of the placed order
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email_id" type="String" required="true" %}
Email ID of the investor
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "wayneReferenceId": "",
    "message": ""
}
```
{% endswagger-response %}
{% endswagger %}

