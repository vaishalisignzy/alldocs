# Lumpsum Buy

You can buy a Mutual Fund and get units and NAV allotted for the investor using the below steps.

1. Create a buy order
2. Confirmation of payment
3. Units and NAV allotment

## Create a buy order

{% swagger method="post" path="create_buy_order" baseUrl="https://<<BASE URL>>/financial_transactions/lumpsum_buy/" summary="Create a lumpsum buy order for a particular scheme." %}
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

{% swagger-response status="201: Created" description="Success" %}
```javascript
{
    "investorId": "",
    "schemeId": "",
    "amount": "",
    "dateTime": "",
    "wayneOrderId": ""
}
```
{% endswagger-response %}
{% endswagger %}

## Confirmation of payment

{% swagger method="post" path="payment_confirmation" baseUrl="https://<<BASE URL>>/financial_transactions/lumpsum_buy/" summary="Get the confirmation status of the payment against the order." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="wayne_order_id" type="String" required="true" %}
Order ID of the buy order placed in previous step
{% endswagger-parameter %}

{% swagger-parameter in="body" name="investor_id" type="String" required="true" %}
Unique Id of the Investor
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "investorId": "",
    "wayneOrderId": "",
    "bankReferenceNumber": "",
    "paymentStatus": "",
    "dateTimeOfAmountCredited": "",
    "amount": ""
}
```
{% endswagger-response %}
{% endswagger %}

## Units & NAV Allotment

{% swagger method="post" path="units_nav_allotment" baseUrl="https://<<BASE URL>>/financial_transactions/lumpsum_buy/" summary="Get the units and NAV allotted against the order placed." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="investor_id" type="String" required="true" %}
Unique Id of the investor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="wayne_order_id" type="String" required="true" %}
Order ID of the order placed
{% endswagger-parameter %}

{% swagger-parameter in="body" name="bank_reference_number" type="String" required="true" %}
Bank reference number of the amount deposited
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "invetsorId": "",
    "schemeName": "",
    "schemeCode": "",
    "amount": "",
    "navAllotmentDate": "",
    "navAllotted": "",
    "unitsAllotted": ""
}
```
{% endswagger-response %}
{% endswagger %}

## Send confirmation SMS to investor

{% swagger method="post" path="send_confirmation_sms" baseUrl="https://<<BASE URL>>/financial_transactions/lumpsum_buy/" summary="Send a confirmation SMS to the investor with the Units, NAV and other details for the allotment." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="investor_id" type="String" required="true" %}
Unique Id of the investor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="wayne_order_id" type="String" required="true" %}
Order Id of the order placed
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

{% swagger method="post" path="send_confirmation_email" baseUrl="https://<<BASE URL>>/financial_transactions/lumpsum_buy/" summary="Send a confirmation Email to the investor with the Units, NAV and other details for the allotment." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="investor_id" type="String" required="true" %}
Unique id of the investor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="wayne_order_id" type="String" required="true" %}
Order id of the placed order
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

