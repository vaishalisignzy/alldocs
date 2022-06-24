# Update customer details

Update existing customer details using the “Update Entity” API endpoint. Any changes to the existing customer’s address, phone number, or email id can be initiated using the POST HTTP method. Only these strings can be modified using this API, and these changes will not affect the existing customer’s entity ID or KIT number.

{% swagger method="post" path="/updateentity" baseUrl="	https://<< BASE URL>>/Yappay/business-entity-manager" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

#### Request Body

```
{
"entityId": "123453227",
"contactNo": "+931111111111",
"emailAddress": "sanjeevi@gmail.com",
"addressDto": {
"address": [
{
"title": "RESIDENTIAL_PRIMARY",
"address1": "3e,Jai Durgai Nagar,coimbatore",
"address2": "adsda",
"city": "coimbatore",
"state": "Balkh",
"country": "India",
"pinCode": "111111"
}
]
}
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
