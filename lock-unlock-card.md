# Lock/Unlock Card

Initiate a soft unlock or hard unlock of your customer’s card, and if need be, the block card option can be activated. Soft lock requires no action as it can be done or undone by the card owner. A hard lock (Block) option can be enabled when the card is lost or damaged and a new card must be issued.

{% swagger method="post" path="/block" baseUrl="https://<< BASE URL>>/Yappay/business-entity-manager" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

#### Request Body

```
{
"entityId": "BUSINESS12345678",
"flag": "L",
"kitNo": "0000006000591",
"reason": "lock for safety"
}
```

#### Response Body

```
{
"result": {
"status": true
},
"exception": null,
"pagination": null
}

```
