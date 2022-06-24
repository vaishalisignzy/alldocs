# Inserting Checks into Decision Engine

{% swagger baseUrl="https://go-preproduction.signzy.app" path="/api/checks/:applicationId/save" method="post" summary="Save Checks" %}
{% swagger-description %}
This endpoint allows the user to enter a new Check into the system. The underlying details about managing the associated CheckBox will be taken care of automatically.

\




**Note:**

 A possible addition to this endpoint may be a wildcard for the `widgetName` parameter, because of which this created check would be triggered to run every time the Merchant finishes onboarding, regardless of what widgets he chose to fill. 
{% endswagger-description %}

{% swagger-parameter in="path" name="applicationId" type="string" %}
applicationId
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
Authorization Token generated from either application login, or dashboard user login.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="tags" type="object" %}
Contains keys 'passed', 'failed', 'error'. Default values are 'Safe', 'Unsafe', and 'Uncertain' respectively.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="resultLocation" type="object" %}
ID of the page the result should be stored in. Defaults to `pageId` parameter.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="dataSource" type="object" %}
Structure depends on `operation` assigned. More details below.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="operation" type="string" %}
Operation assigned. This will decide the type of data sent using dataSource parameter. Can be 'checkpoints', 'boolean', or 'truthtable'.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="widgetName" type="string" %}
Name of a widget - will determine if this Check is run - by checking what widget the Merchant chose to fill.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="level" type="number" %}
Level of the Check. Defaults to 0.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pageId" type="string" %}
ID of the page - will determine what if this Check is run after being paired with `widgetNames`.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="flowId" type="string" %}
ID of the flow - will determine if this Check will be run - by checking the Merchant's assigned flow.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="string" %}
Name of the Check.
{% endswagger-parameter %}

{% swagger-response status="200" description="Returns the Check object stored." %}
```
<<TO BE UPDATED>>
```
{% endswagger-response %}

{% swagger-response status="400" description="Could not find a cake matching this query." %}
```
{
    "error": {
        "statusCode": 422,
        "name": "Error",
        "message": "'dataSource.value.type' and 'dataSource.value.data' must be specified",
        "details": {}
    }
}
```
{% endswagger-response %}
{% endswagger %}

### Operation Types & associated dataSource parameter

{% tabs %}
{% tab title="boolean" %}
Boolean type of operation is to compare two different variables available in a Merchant's entered data in a boolean fashion. It takes in a Fact, a Value, and a boolean operator, much like a popular library by the name of `json-rules-engine`.

**String and Numeric operators:**

`equal` - _fact_ must equal _value_

`notEqual` - _fact_ must not equal _value_

_these operators use strict equality (===) and inequality (!==)_

**Numeric operators:**

`lessThan` - _fact_ must be less than _value_

`lessThanInclusive`- _fact_ must be less than or equal to _value_

`greaterThan` - _fact_ must be greater than _value_

`greaterThanInclusive`- _fact_ must be greater than or equal to _value_

**Array operators:**

`in` - _fact_ must be included in _value_ (an array)

`notIn` - _fact_ must not be included in _value_ (an array)

`contains` - _fact_ (an array) must include _value_

`doesNotContain` - _fact_ (an array) must not include _value_

```
{
    "boolean": "equal", // Operator assigned
    // For using the result of earlier Checks
    "fact": {
        "type": "check",
        "data": "<<checkId>>"
    },
    // OR
    // For using the result of a Signzy API
    "fact": {
        "type": "api",
        "data": {
            "apiId": "",
            "type": "",
            "mapping": ""
        } // Eg. PanNameScore
		}
		// Fact or Value can be provided with type `pageVariable`
    "value": {
        "type": "pageVariable",
        "data": {
            "pageId": "<<pageId>>", // Eg. 5dc960656a15482e45664c86
            "variable": "<<variableName>>", // Eg. PanNameName
        }
    }
    // OR
    // Value can also be hardcoded
    "value": {
        "type": "hardcoded",
        "data": "<<hardcoded string>>"
    }
}
```
{% endtab %}

{% tab title="checkpoints" %}
Checkpoints type of operation services requests to tag an API output parameter in the form of a floating point value which denotes the closeness of a given value to that extracted from a document. This can be tagged with any value required.

```
{
    "checkpoints": {
        "0.2": "foo",
        "0.6": "bar",
        "1.0": "success!"
    }, // If Score specified in apiParam is 0.5, result is 'bar'
    "apiParam": {
        "apiId": "",
        "type": "",
        "mapping": ""
    } // Eg. NameScore
}
```
{% endtab %}

{% tab title="truthtable" %}
TruthTable type of operation is reserved for denoting Decisions and separating them from normal checks. To create this type of Check -

1. Get template sheet using `/api/checks/getTemplateSheet` as mentioned in the document 'Getting Template Sheets for Decision Engine'
2. Fill it up with Result Values (as explained in `Concepts` document under the `Decision` section)
3. Upload sheet containing data to `https://persist.signzy.tech/api/files/upload` with form-data containing `file` (containing a MultipartFile) parameter before calling this.

```
{
    // Link to the sheet from which truth table will be parsed
    "sheet": "https://persist.signzy.com/fooBar"
}
```
{% endtab %}
{% endtabs %}
