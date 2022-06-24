---
description: Transactions status by External Id
---

# View txn status by External ID

This API can be used to query the status of a transaction using the partner’s transaction id shared as part of the original API call. This is only applicable for Financial transactions.

{% swagger method="get" path="/{extTrxId}" baseUrl="https://<< BASE URL>>/Yappay/txn-manager/fetch" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

#### Request Body 

```
"/Yappay/txn-manager/fetch/PRDEMO1234567"
```

#### Response Body

```
{
"result": {
"transaction": {
"amount": "2.0",
"balance": 2,
"transactionType": "M2C",
"type": "CREDIT",
"time": 1503668261000,
"txRef": 857207461,
"businessId": null,
"beneficiaryName": "testMer1 siva",
"beneficiaryType": null,
"beneficiaryId": "60390MER",
"description": "Change",
"otherPartyName": "testMer1 siva",
"otherPartyId": "60390MER",
"txnOrigin": "MOBILE",
"transactionStatus": "PAYMENT_SUCCESS",
"status": null,
"yourWallet": "GENERAL",
"beneficiaryWallet": "",
"externalTransactionId": "113476XX191",
"retrivalReferenceNo": null,
"authCode": null,
"billRefNo": null,
"bankTid": "853225126"
},
"balance": null
},
"exception": null,
"pagination": null
}
```
