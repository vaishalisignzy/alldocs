# Get Page Information

{% swagger baseUrl="https://go-preproduction.signzy.app" path="/api/applications/:applicationId/distributor/pages/:pageId" method="post" summary="Get Page Information" %}
{% swagger-description %}
After merchant login this API fetches all the meta-data information for a page which in turn is used to submit a step. 
{% endswagger-description %}

{% swagger-parameter in="path" name="pageId" type="string" %}
Landing Page from the Merchant Login.
{% endswagger-parameter %}

{% swagger-parameter in="path" name="applicationId" type="string" %}
Application Id for that merchant.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Authentication token from Merchant Login. `id` of Merchant.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="flowType" type="string" %}
Type of the flow (mainflow/subflow)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="uid" type="string" %}
Merchant Id
{% endswagger-parameter %}

{% swagger-response status="200" description="Successful" %}
```
{
    "result": {
        "pageName": "...pageName...",
        "apiIds": {
            "widget_apiId": "...widget_apiId..."
        },
        "pageType": "...pageType...",
        "pageTitle": "...pageTitle...",
        "widgets": [{
            "apiName": "...apiName...",
            "document": "...document...",
            "uiConfig": [{
                    "variableName1": "...variableName1...",
                    "dataValue1": "...dataValue1..."
                },
                {
                    "variableName2": "...variableName2...",
                    "dataValue2": "...dataValue2..."
                },
                {
                    "variableName3": "...variableName3...",
                    "dataValue3": "...dataValue3..."
                }
            ],
            "widgetType": "...widgetType...",
            "apis": [
                "...widget_apiId..."
            ]
        }]
    }
}
```
{% endswagger-response %}

{% swagger-response status="401" description="Incorrect Credentials" %}
```
{
    "error": {
        "statusCode": 401,
        "name": "Error",
        "message": "Authorization Required",
        "code": "AUTHORIZATION_REQUIRED"
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
    flowType: "...flowType...",
    uid: "...uid..."
}
```

#### Request Field Description

| Key      | Type   | Description                             |
| -------- | ------ | --------------------------------------- |
| flowType | string | Type of the flow (Mainflow or subflow)  |
| uid      | string | Signzy Merchant Id after Merchant Login |
{% endtab %}

{% tab title="Sample Response Body" %}
```
{
    "result": {
        "pageName": "...pageName...",
        "apiIds": {
            "widget_apiId": "...widget_apiId..."
        },
        "pageType": "...pageType...",
        "pageTitle": "...pageTitle...",
        "widgets": [{
            "apiName": "...apiName...",
            "document": "...document...",
            "uiConfig": [{
                    "variableName1": "...variableName1...",
                    "dataValue1": "...dataValue1..."
                },
                {
                    "variableName2": "...variableName2...",
                    "dataValue2": "...dataValue2..."
                },
                {
                    "variableName3": "...variableName3...",
                    "dataValue3": "...dataValue3..."
                }
            ],
            "widgetType": "...widgetType...",
            "apis": [
                "...widget_apiId..."
            ]
        }]
    }
}
```

#### Response Field Description

| Key                                 | Type           | Description                                                                        |
| ----------------------------------- | -------------- | ---------------------------------------------------------------------------------- |
| pageNumber                          | int            | Number of the page.                                                                |
| widget\_aipId                       | string         |                                                                                    |
| pageType                            | string         | Type of the page.                                                                  |
| pageTitle                           | string         | Title of the page.                                                                 |
| widgets                             | array (object) | Array if Objects. Contains details about each widget in Object and forms an array. |
| widget\[...]._apiName_              | string         | Name of the API                                                                    |
| widget\[...]._document_             |                |                                                                                    |
| widget\[...]._uiConfig_             | array (object) | Object containing name of the variable and assigned data values.                   |
| widget\[...]._variableName**\<n>**_ | string         | Name of the variable in the widget.                                                |
| widget\[...]._dataValue**\<n>**_    | string         | Data corresponding to the variable name in the widget.                             |
| widget\[...]._widgetType_           | string         | Type of the widget                                                                 |
| widget\[...]._apis_                 | array          | List of APIs associated to the widgets.                                            |
{% endtab %}
{% endtabs %}

