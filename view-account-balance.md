# View account balance

Fetch your customer’s account balance with this API endpoint. The Customer’s Entity ID is used to check the balance. This request uses the GET Http type of query to retrieve the details.

{% swagger method="get" path="/{entityId}" baseUrl="https://<< BASE URL>>/Yappay/business-entity-manager/fetchbalance" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

#### Request Body

```json
"/Yappay/business-entity-manager/fetchbalance/123453227"

```

#### Response Body

```
{
"result": [
{
"entityId": "E12345678",
"productId": "GENERAL",
"yseId": null,
"balance": "98.0"
}
],
"exception": null,
"pagination": null
}
```
