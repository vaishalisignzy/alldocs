# Systematic Sell

You can sell a Mutual Fund using SWP (Systematic Withdrawal Plan) and get the money credited to investor's default bank account using the below steps.

1. Create a SWP order
2. Units and NAV confirmation for each of SWP order
3. Credit of money to the investor's bank account for each of SWP order

## Create a SWP order

You can create a SWP order either by the amount you want to sell or the units you want to sell.

### Create a SWP order by amount

{% swagger method="post" path="create_swp_order_by_amount" baseUrl="https://<<BASE URL>>/financial_transactions/systematic_sell/" summary="Create a SWP order for a particular scheme by the amount you want to sell." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="investor_id" type="String" required="true" %}
Unique ID of the investor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="scheme_id" type="String" required="true" %}
ID of the scheme in which Mutual Fund sell is to be done
{% endswagger-parameter %}

{% swagger-parameter in="body" name="amount" type="String" required="true" %}
Amount of money for which the mutual fund is to be sold
{% endswagger-parameter %}

{% swagger-parameter in="body" name="start_date" type="String" required="true" %}
Date of start
{% endswagger-parameter %}

{% swagger-parameter in="body" name="end_date" type="String" required="true" %}
End date
{% endswagger-parameter %}

{% swagger-parameter in="body" name="number_of_installments" type="String" required="true" %}
Number of installment
{% endswagger-parameter %}

{% swagger-parameter in="body" name="frequency" type="Enums" required="true" %}
Monthly, Quarterly, Half-Yearly, Yearly
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

### Create a SWP order by units

{% swagger method="post" path="create_swp_order_by_units" baseUrl="https://<<BASE URL>>/financial_transactions/systematic_sell/" summary="Create a SWP order for a particular scheme by the units you want to sell." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="investor_id" type="String" required="true" %}
Unique ID of the investor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="scheme_id" type="String" required="true" %}
ID of the scheme in which Mutual Fund sell is to be done
{% endswagger-parameter %}

{% swagger-parameter in="body" name="units" type="String" required="true" %}
Number of units for which the mutual fund is to be sold
{% endswagger-parameter %}

{% swagger-parameter in="body" name="start_date" type="String" required="true" %}
Start date of SWP
{% endswagger-parameter %}

{% swagger-parameter in="body" name="end_date" type="String" required="true" %}
End date of SWP
{% endswagger-parameter %}

{% swagger-parameter in="body" name="number_of_installmentss" type="String" required="true" %}
Number of installments
{% endswagger-parameter %}

{% swagger-parameter in="body" name="frequency" type="String" required="true" %}
Monthly, Quarterly, Half-Yearly, Yearly
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

## Units & NAV Confirmation For Each Of SWP Order

{% swagger method="post" path="units_nav_confirmation" baseUrl="https://<<BASE URL>>/financial_transactions/systematic_sell/" summary="Get the units and NAV confirmed against each of the SWP order placed." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="investor_id" type="String" required="true" %}
Unique Id of the investor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="wayne_swp_id" type="String" required="true" %}
SWP ID of the order placed
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "invetsorId": "",
    "schemeName": "",
    "schemeCode": "",
    "amount": "",
    "navConfirmationDate": "",
    "navConfirmed": "",
    "unitsSold": ""
}
```
{% endswagger-response %}
{% endswagger %}

## Credit of money to the investor's bank account for each of SWP order

{% swagger method="post" path="credit_money" baseUrl="https://<<BASE URL>>/financial_transactions/systematic_sell/" summary="Get the payment credited to the default bank account of the investor for each of SWP order." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="wayne_swp_id" type="String" required="true" %}
SWP ID of the sell order placed in previous step
{% endswagger-parameter %}

{% swagger-parameter in="body" name="investor_id" type="String" required="true" %}
Unique Id of the Investor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="bank_account_number" type="String" required="true" %}
Default bank account number of the Investor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ifsc_code" type="String" required="true" %}
IFSC code of the bank
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

## Send confirmation SMS to investor

{% swagger method="post" path="send_confirmation_sms" baseUrl="https://<<BASE URL>>/financial_transactions/systematic_sell/" summary="Send a confirmation SMS to the investor with the Units, NAV and other details for the sell of mutual fund." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="investor_id" type="String" required="true" %}
Unique Id of the investor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="wayne_swp_id" type="String" required="true" %}
SWP Id of the order placed
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

{% swagger method="post" path="send_confirmation_email" baseUrl="https://<<BASE URL>>/financial_transactions/systematic_sell/" summary="Send a confirmation Email to the investor with the Units, NAV and other details for the sell of the mutual fund." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="investor_id" type="String" required="true" %}
Unique id of the investor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="wayne_swp_id" type="String" required="true" %}
SWP id of the placed order
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

