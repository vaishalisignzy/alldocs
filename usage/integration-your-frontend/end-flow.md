# Application Submission

{% swagger baseUrl="https://go-preproduction.signzy.app" path="/api/merchants/:merchantId/status" method="post" summary="Submit the application" %}
{% swagger-description %}
This API is used to change merchant application's status to pending so that it can flow to backops.
{% endswagger-description %}

{% swagger-parameter in="path" name="merchantId" type="string" %}
Merchant User Id
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Authentication token of the Merchant 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="status" type="string" %}
To be sent as "pending" in order to end the flow
{% endswagger-parameter %}

{% swagger-response status="200" description="Successful" %}
```
{
    "result": {
        "status": "...status..."
    }
}
```
{% endswagger-response %}
{% endswagger %}

#### Sample request-response and field description

{% tabs %}
{% tab title="Sample Request Body" %}
```
{
    status: "...status..."
}
```

#### Request Field Description

| Key    | Type   | Description                                                                                |
| ------ | ------ | ------------------------------------------------------------------------------------------ |
| status | string | <p>Fixed String: "<em><strong>Pending</strong></em> ".</p><p>In order to end the flow.</p> |
{% endtab %}

{% tab title="Sample Response Body" %}
```
{
    "result": {
        "status": "...status..."
    }
}
```

#### Response Field Description

| Key    | Type   | Description                               |
| ------ | ------ | ----------------------------------------- |
| status | string | Updated Status after submitting the form. |
{% endtab %}
{% endtabs %}
