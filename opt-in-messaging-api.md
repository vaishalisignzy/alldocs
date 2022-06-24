# Opt-in Messaging API

{% swagger baseUrl="https://staging.signzy.xyz/" path="organs/whatsapp/api/userConsent" method="post" summary="Post User Consent for Opting in WhatsApp" %}
{% swagger-description %}
This endpoint allows you to take consent from the user.
{% endswagger-description %}

{% swagger-parameter in="query" name="countryCode" type="string" %}
This is the mobile number’s country code.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="mobileNumber" type="string" %}
This is the WhatsApp number for Opting in for messages.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="otpVerified" type="boolean" %}
If the registered number is different from the provided WhatsApp number, then OTP verification needs to be done from the WhatsApp number and provide the value true.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="customerId" type="string" %}
This is the ID of the customer in case the particular customer details usage report needs to be provided. It is optional if no usage report is needed.
{% endswagger-parameter %}

{% swagger-parameter in="query" name="productId" type="string" %}
This is the identity of the product who will use this service.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="countryCode" type="string" %}

{% endswagger-parameter %}

{% swagger-response status="200" description="Cake successfully retrieved." %}
```
```
{% endswagger-response %}

{% swagger-response status="302" description="" %}
```
```
{% endswagger-response %}

{% swagger-response status="404" description="Could not find a cake matching this query." %}
```
{    "message": "Ain't no cake like that."}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://staging.signzy.xyz/" path="organs/whatsapp/api/userConsent" method="post" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="query" name="productId" type="string" %}

{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
```
{% endswagger-response %}
{% endswagger %}

```javascript
{ 
    "response": {
        "id": "3795200898494416206",
        "phone": "",
        "details": "OPT_IN",
        "status": "success"
    },
    "data": {
        "response_messages": [
            {
                "id": "3795200898494416206",
                "phone": "919777777778",
                "details": "OPT_IN",
                "status": "success"
            }
        ]
    }
}
```

