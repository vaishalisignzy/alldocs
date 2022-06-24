---
description: Enabling Customer for QR payments
---

# Make QR payment

Enable the customer to pay at any QR-enabled merchant. While calling this API endpoint, no other customer details will be authenticated, and payments happen according to rules set by the Bharat QR portal. This API is applicable only for debit transactions and can be used to pay any QR merchant or store.

{% swagger method="get" path="/payment" baseUrl="https://<< BASE URL>>/Yappay/payment-manager" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

#### Request Body

```
{
"merchantData": "000201010211021540000100000019406156000010000001945204737953033565802IN5908\r\nTestER296007Chennai610662552763047144",
"fromEntityId": "4011000048",
"toEntityId": "",
"productId": "GENERAL",
"description": "test",
"amount": "2",
"transactionType": "PURCHASE",
"transactionOrigin": "MOBILE",
"externalTransactionId": "3970540326",
"businessType": "PRDEMO",
"businessEntityId": "PRDEMO",
"firstName": "test",
"lastName": "",
"contactNo": "+914011000048",
"senderCardNo": "6000300000900009",
"billRefNo": "0767469687",
"additionalData": "01"
}
```

#### Response Body

```
{
"result": {
"txId": 12345678901,
"retrivalReferenceNo": "704618883422",
"authCode": "717089",
"action": "Success"
},
"exception": null,
"pagination": null
}
```

\
