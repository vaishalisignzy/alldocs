# Text Match

The purpose of text match is to quickly test out whether the user data entered is valid and matches the document. For example: Name/DOB in Aadhar card. This API matches the fields on recorded ID card to the ones we provide and from here we can decide whether the user has provided correct information against the ID card.

The users need to upload an image of the particular ID card to match. Placing direct URLs in place of ID cards, in case you have them, is also permissible.

For best results, please make sure the image you use fits tightly in camera view and is horizontally-aligned.&#x20;

**Please note that each image/pdf should be less than 2MB.**

There are two important properties to note:

* essentials - This is the property which holds data for processing.
* fields - These are the data fields with values.

{% swagger baseUrl="https://signzy.tech" path="/api/v2/patrons/..patron-id.../textmatches" method="post" summary="Text Match" %}
{% swagger-description %}
This method matches the text fields of ID cards
{% endswagger-description %}

{% swagger-parameter in="body" name="essentials.fields" type="string" %}
The text fields to be compared
{% endswagger-parameter %}

{% swagger-parameter in="body" name="essentials.images" type="string" %}
URL to the image which contains the text
{% endswagger-parameter %}

{% swagger-parameter in="body" name="essentials" type="string" %}
Contains the essential input data
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "essentials": {
        "images": [
            "...url..to..the..image..."
        ],
        "fields": {

            "..field1..":"..it's value..",
            "..field2..":"..it's value..",
            ..
            ..
            ..
            ..
            "..fieldN..":"..it's value.."
        }
    },
    "id": "5bxxxxxxxxxx474",
    "patronId": "5a9xxxxxxxxxxxx119d8",
    "result": {
            "field1": {
                "score": "score between 0-1",
                "verb": "NO MATCH/MATCH/PARTIAL MATCH",
                "bestMatch": "Best Match found"
            },
            "field2": {
                "score":  "score between 0-1",
                "verb": "NO MATCH/MATCH/PARTIAL MATCH",
                "bestMatch": "Best Match found"
            },
            ..
            ..
            ..
            "fieldN": {
                "score": "score between 0-1",
                "verb": "NO MATCH/MATCH/PARTIAL MATCH",
                "bestMatch": "Best Match found"
            }
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
"images":["..url..to..the..image.."],
"fields": {

   "..field1..":"..it's value..",
   "..field2..":"..it's value..",
   ..
   ..
   ..
   ..
   "..fieldN..":"..it's value.."

 }
```
{% endtab %}

{% tab title="Response Parameter" %}
| Parameter Name   | Description                                                                                  |
| ---------------- | -------------------------------------------------------------------------------------------- |
| result           | Contains the fields which contain the compared text and displays the match/no match scenario |
| field1.score     | Score between 0 and 1                                                                        |
| field1.verb      | NO MATCH/MATCH/PARTIAL MATCH                                                                 |
| field1.bestMatch | Best Match Found                                                                             |
{% endtab %}
{% endtabs %}

