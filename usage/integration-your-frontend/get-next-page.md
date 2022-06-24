# Get Next Page

{% swagger baseUrl="https://go-preproduction.signzy.app" path="/api/flows/:flowId/distributor/:distributorId/getNextPage" method="post" summary="Get Next Page" %}
{% swagger-description %}
This API is used to fetch the next step (page id) of the flow.
{% endswagger-description %}

{% swagger-parameter in="path" name="distributorId" type="string" %}
Application Id of the merchant
{% endswagger-parameter %}

{% swagger-parameter in="path" name="flowId" type="string" %}
Flow Id of the merchant
{% endswagger-parameter %}

{% swagger-parameter in="header" name="ApplicationId" type="string" %}
Application Id of the merchant
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Authentication token of the Merchant fetching the next Page on submit.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="isSubflow" type="boolean" %}
True / False. If the flow is a sub flow or not.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pageId" type="string" %}
Id of the current Page
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pageName" type="string" %}
Name / Title of the current Page
{% endswagger-parameter %}

{% swagger-parameter in="body" name="uid" type="string" %}
Id of the Logged In Merchant
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data" type="object" %}
User data to be submitted
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pageType" type="string" %}
Type of Page
{% endswagger-parameter %}

{% swagger-response status="200" description="Successful" %}
```
{
    "result": {
        "pageId": "...pageId..."
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
    isSubflow: ...isSubFlow...,
    pageId: "...pageId...",
    pageName: "...pageName...",
    uid: "...uid...",
    data: {....},
    pageType: "...pageType..."
}
```

#### Request Field Description

| Key       | Type    | Description                             |
| --------- | ------- | --------------------------------------- |
| isSubflow | boolean | If the current flow is a subflow or not |
| pageId    | string  | Signzy Id of the current page           |
| pageName  | string  | Name / Title of the current page.       |
| uid       | string  | Id of the logged in Merchant            |
| pageType  | string  | Type of the page                        |
| data      | object  | User data to be submitted.              |
{% endtab %}

{% tab title="Sample Response Body" %}
```
{
    "result": {
        "pageId": "...pageId..."
    }
}
```

#### Response Field Description

| Key    | Type   | Description                               |
| ------ | ------ | ----------------------------------------- |
| pageId | string | Next Page Id to be queried on form submit |
{% endtab %}
{% endtabs %}

