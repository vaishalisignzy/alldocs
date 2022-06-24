# ID Classification

The purpose of this ID Classification is to test out whether the image entered by the user is a valid Emirates ID Card or a Passport Image. This check should be performed before OCR and it ensures that the application accepts only valid id cards for OCR.

The users need to upload an image of the particular ID card to classify. Placing direct URLs in place of ID cards, in case you have them, is also permissible.

For best results, please make sure the image you use fits tightly in camera view and is horizontally-aligned.&#x20;

**Please note that each image/pdf should be less than 2MB.**

There are four important properties to note:

* essentials - This is the property which holds data for processing.
* essentials.files - These are the URLs of the images to check.
* task - The value of this parameter for this request will be "classification"
* country - This is the 3 digit ISO code for the country mentioned in the passport

{% swagger baseUrl="https://signzy.tech" path="/api/v2/patrons/..patron-id.../foreignidentitiesextractions" method="post" summary="ID Classification" %}
{% swagger-description %}
This method classifies the URL as Emirates ID or Passport or Unknown for United Arab Emirates
{% endswagger-description %}

{% swagger-parameter in="body" name="country" type="string" %}
3 letter ISO Code of the country. ARE for United Arab Emirates
{% endswagger-parameter %}

{% swagger-parameter in="body" name="task" type="string" %}
should be classification for all Foreign ID Classification
{% endswagger-parameter %}

{% swagger-parameter in="body" name="essentials.files" type="array" %}
URL to the images to classify
{% endswagger-parameter %}

{% swagger-parameter in="body" name="essentials" type="string" %}
Contains the essential input data
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "essentials": {
        "files": [
            "...url..to..the..image..."
        ]
    },
    "id": "5bxxxxxxxxxx474",
    "patronId": "5a9xxxxxxxxxxxx119d8",
    "task": "classification",
    "country": "ARE"
    "result": {
        "idType":"passport/emiratesId/unknown",
        "status":"200",
        "message":"success"
    }
}

```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="Request Schema" %}
```
{
    "essentials": {
    "files":["..url..to..the..image.."],
    "task": "classification",
    "country": "ARE"
}
```
{% endtab %}

{% tab title="Response Parameter" %}
| Parameter Name | Description                                                    |
| -------------- | -------------------------------------------------------------- |
| result         | Contains the fields which contain the idType of the image URLs |
| result.idType  | passport/emiratesId/unknown                                    |
| result.status  | StatusCode of the request                                      |
| result.message | Message to explain the status of the request                   |
{% endtab %}
{% endtabs %}

### Rules for Classification

1. We will read the MRZ or the Machine Readable Zone code from the ID Card Image
2. The extracted MRZ will be compared with the following rule:&#x20;
   1. Emirates ID: 1st Line of MRZ should have ILARE followed by Emirates ID Number. Here IL is the type of ID Card and ARE is the country code for United Arab Emirates.&#x20;
   2. Passport: 1st Line of MRZ should match with the specification: P\<ARE\<surname<\<given\<name<<. Here P stands for Passport and ARE is the country code for United Arab Emirates.&#x20;
