---
description: Credit customer card
---

# Credit customer account

{% swagger method="post" path="/create" baseUrl="	https://<< BASE URL>>/Yappay/txn-manager" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

Approve credit requests to your customer’s card/ account with this API. This transaction will happen in case of any payment reversal to the customer’s card.

#### &#x20;Request Body

```
{
"toEntityId": "123453227",
"fromEntityId": "PRDEMO01",
"yapcode": "1234",
"productId": "GENERAL",
"description": "transferfunds",
"amount": 100,
"transactionType": "M2C",
"business": "PRDEMO",
"businessEntityId": "PRDEMO",
"transactionOrigin": "MOBILE",
"externalTransactionId": "PRDEMO1234j5j67"
}
```

#### Response Body

```
{
"result": {
"txId": 667373359
},
"exception": null,
"pagination": null
}
```
