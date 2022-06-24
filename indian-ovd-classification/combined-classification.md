# Combined Classification

## Classification of Identity card

The Identity Card reading system accepts direct URL to the front and back sides.&#x20;

{% swagger baseUrl="https://preproduction.signzy.tech" path="/api/v2/snoops" method="post" summary="Identity Card Extraction" %}
{% swagger-description %}
**Production URL:**

\




`https://signzy.tech/api/v2/snoops`

\




\


This method allows classification of Indian OVDs. 
{% endswagger-description %}

{% swagger-parameter in="body" name="essentials,summary" type="string" %}
This parameter needs to be set to true to get the combined OCR response in output
{% endswagger-parameter %}

{% swagger-parameter in="body" name="essentials" type="string" %}
Contains essential input data
{% endswagger-parameter %}

{% swagger-parameter in="body" name="accessToken" type="string" %}
Contains the identity access token.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="task" type="string" %}
The task to be performed - Classification
{% endswagger-parameter %}

{% swagger-parameter in="body" name="itemId" type="string" %}
Contains the identity item id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="service " type="string" %}
Classifies the type of service - Identity
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "essentials": {
        "files": ["..url..to..the..image.."]
    },
    "id": "...id...",
    "patronId": "...patronId...",
    "task": "classify",
    "result": [{
        "status": "success",
        "classification": {
            "status": "success",
            "idType": "aadhaar/individualPan/businessPan/unknownPan/passport/dl/unknown",
            "message": "Successfully completed."
        }
    }]
}


```
{% endswagger-response %}
{% endswagger %}

### All ID Classification

{% tabs %}
{% tab title="Request Schema" %}
```
{
        "service":"Identity",
        "itemId":"<Identity-id>",
        "task":"classify",
        "accessToken":"<Identity-access-token>",
        "essentials":{}
}
```
{% endtab %}

{% tab title="Response Parameter" %}
| Parameter Name                | Data Length | Data Type | Description                                                      |
| ----------------------------- | ----------- | --------- | ---------------------------------------------------------------- |
| result.status                 | 20          | string    | success or failure                                               |
| result.classification.status  | 20          | string    | success or failure                                               |
| result.classification.idType  | 20          | string    | aadhaar/individualPan/businessPan/unknownPan/passport/dl/unknown |
| result.classification.message | 100         | string    | Successfully completed or Error                                  |
{% endtab %}
{% endtabs %}

