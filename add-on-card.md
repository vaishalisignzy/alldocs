---
description: Adding a card to the customer’s account
---

# Add-on card

Add a virtual add-on card to your customer’s account without any modifications to the customer’s records. Adding a card doesn’t require any repetition of the onboarding process. This API endpoint is usually applicable for virtual cards. They are called using the POST Http method with request and response in JSON.

{% swagger method="get" path="/addCard" baseUrl="https://<< BASE URL>>/Yappay/business-entity-manager" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

#### Request Body

```
{
"entityId": "123453227",
"kitNo": "900009910",
"cardType": "P",
"business": "PRDEMO"
}
```

#### Response Body

```
{
"result": {
"Status": true
},
"exception": null,
"pagination": null
}
```
