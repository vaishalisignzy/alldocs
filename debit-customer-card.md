# Debit customer card

Authorize and validate any debit transactions arising from your customer’s card using this POST Http request. The customer’s entity ID, along with the parameters of product ID, transaction type, external transaction ID, and so on, will be called when deploying this API.

{% swagger method="get" path="/direct" baseUrl="	https://<< BASE URL>>/Yappay/txn-manager/create" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

#### Request Body

```
{
"toEntityId": "PRDEMO",
"fromEntityId": "123453227",
"productId": "GENERAL",
"description": "Change",
"amount": 10,
"transactionType": "C2M",
"transactionOrigin": "MOBILE",
"businessType": " PRDEMO ",
"businessEntityId": " PRDEMO ",
"externalTransactionId": "PRDEMOj839140170j"
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
