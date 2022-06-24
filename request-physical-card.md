---
description: Converting virtual card to physical card
---

# Request Physical Card

It is used to convert virtual card to physical card and it will be dispatch to the customer's registered address. This API endpoint is usually applicable for virtual cards. They are called using the POST Http method with request and response in JSON.

{% swagger method="post" path="/requestPhysicalCard" baseUrl="https://<< BASE URL>>/Yappay/business-entity-manager" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

#### Request Body

```
{
"entityId": "M2P_TEST",
"kitNo": "114000000",
"addressDto": {
"address": [
{
"title": "DELIVERY",
"address1": "my address, my street",
"address2": "my locality",
"address3": "Chennnai",
"city": "mycity",
"state": "mystate",
"country": "India",
"pinCode": "6000061"
}
]
}
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
