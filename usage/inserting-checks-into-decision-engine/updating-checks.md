# Updating Checks

{% swagger baseUrl="https://go-preproduction.signzy.app" path="/api/checks/update" method="put" summary="Update Checks" %}
{% swagger-description %}
This endpoint allows the user to edit an existing Check within the system. The underlying details about managing the associated CheckBox will be taken care of automatically.
{% endswagger-description %}

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

{% swagger-parameter in="body" name="checkId" type="string" %}
ID of the Check which is being edited.
{% endswagger-parameter %}

{% swagger-response status="200" description="Returns the Check object updated." %}
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
