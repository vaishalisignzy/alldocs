---
description: Replacing stolen/damaged card
---

# Replace a card

This call can be used to issue a new card to a customer in the event of card theft or damage. This API is applicable if the customer’s card is voluntarily blocked. The parameters of Entity Id, current KIT no and new KIT number needs to be called. The replacement will trigger the transfer of transaction history and customer details to the new card. The old card needs to be permanently barred before raising this request.

{% swagger method="post" path="replaceCard" baseUrl="https://<< BASE URL>>/Yappay/business-entity-manager" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

#### Request Body

```
{
"entityId": "123453227",
"oldKitNo": "900009910",
"newKitNo": "900009911"
}
```

#### Response Body

```
{
"status": true,
"exception": null,
"pagination": null
}
```
