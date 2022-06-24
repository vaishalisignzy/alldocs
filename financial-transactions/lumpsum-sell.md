# Lumpsum Sell

You can sell a Mutual Fund and get the money credited to investor's default bank account using the below steps.

1. Create a sell order
2. Units and NAV confirmation
3. Credit of money to the investor's bank account

## Create a sell order

You can create a sell order either by the amount you want to sell or the units you want to sell.

### Create a sell order by amount

{% swagger method="post" path="create_sell_order_by_amount" baseUrl="https://<<BASE URL>>/financial_transactions/lumpsum_sell/" summary="Create a lumpsum sell order for a particular scheme by the amount you want to sell." %}
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

### Create a sell order by units

{% swagger method="post" path="create_sell_order_by_units" baseUrl="https://<<BASE URL>>/financial_transactions/lumpsum_sell/" summary="Create a lumpsum sell order for a particular scheme by the units you want to sell." %}
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

## Units & NAV Confirmation

{% swagger method="post" path="units_nav_confirmation" baseUrl="https://<<BASE URL>>/financial_transactions/lumpsum_sell/" summary="Get the units and NAV confirmed against the sell order placed." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="investor_id" type="String" required="true" %}
Unique Id of the investor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="wayne_order_id" type="String" required="true" %}
Order ID of the order placed
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

## Credit of money to the investor's bank account

{% swagger method="post" path="credit_money" baseUrl="https://<<BASE URL>>/financial_transactions/lumpsum_sell/" summary="Get the payment credited to the default bank account of the investor." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="wayne_order_id" type="String" required="true" %}
Order ID of the buy order placed in previous step
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

{% swagger method="post" path="send_confirmation_sms" baseUrl="https://<<BASE URL>>/financial_transactions/lumpsum_sell/" summary="Send a confirmation SMS to the investor with the Units, NAV and other details for the sell of mutual fund." %}
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

{% swagger method="post" path="send_confirmation_email" baseUrl="https://<<BASE URL>>/financial_transactions/lumpsum_sell/" summary="Send a confirmation Email to the investor with the Units, NAV and other details for the sell of the mutual fund." %}
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

