# Deleting Checks

{% swagger baseUrl="https://go-preproduction.signzy.app" path="/api/checks/:id" method="delete" summary="Delete Checks" %}
{% swagger-description %}
This endpoint allows you to get free cakes.
{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="string" %}
ID of the Check to delete.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
Authorization Token generated from application login or dashboard users login.
{% endswagger-parameter %}

{% swagger-response status="200" description="Check successfully deleted" %}
```
{
    "result": "ok"
}
```
{% endswagger-response %}

{% swagger-response status="400" description="Something in the request was missing or invalid." %}
```
{
    "error": {
        "statusCode": 400,
        "name": "Error",
        "message": "'dataSource.value' must be specified",
        "details": {}
    }
}
```
{% endswagger-response %}
{% endswagger %}

