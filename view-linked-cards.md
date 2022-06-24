---
description: Retrieve linked cards
---

# View linked cards

Fetch the details of all the cards linked to your customer’s entity ID. The request is raised using the Entity ID of the Customer. The response usually contains the fields of card network, card status, and expiry date of all cards linked to a particular customer.

{% swagger method="get" path="/getCardList" baseUrl="https://<< BASE URL>>/Yappay/business-entity-manager/v3" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

#### Request Body

```
{
"entityId": "123453227"
}
```

#### Response Body

```
{
"result": {
"cardList": [
"5123XXXXXXX1234"
],
"kitList": [
"00000123456"
],
"expiryDateList": [
"1022"
],
"cardStatusList": [
"ALLOCATED"
],
"cardTypeList": [
"PHYSICAL"
]
},
"exception": null,
"pagination": null
}
```
