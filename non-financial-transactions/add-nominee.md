# Add Nominee

You can add a new nominee using the below API endpoint. You can add a maximum of 3 nominees.

## Add Nominee Details

{% swagger method="post" path="/add_nominee" baseUrl="https://<<BASE URL>>/service_requests" summary="Add a nominee to the Investor's folio or account." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="nominee_name" type="String" required="true" %}
Name of the nominee
{% endswagger-parameter %}

{% swagger-parameter in="body" name="nominee_email_id" type="String" required="true" %}
Email ID of the nominee
{% endswagger-parameter %}

{% swagger-parameter in="body" name="nominee_mobile_number" type="String" required="true" %}
Mobile number of the nominee
{% endswagger-parameter %}

{% swagger-parameter in="body" name="relationship_with_nominee" type="Enums" required="true" %}
Relationship with the nominee
{% endswagger-parameter %}

{% swagger-parameter in="body" name="nominee_date_of_birth" type="Date" required="true" %}
Date of birth of the nominee
{% endswagger-parameter %}

{% swagger-parameter in="body" name="percentage_ownership" type="Double" required="true" %}
Percentage of ownership
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pan_number" type="String" required="true" %}
PAN number of the Investor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="wid" type="String" %}
Wayne Investor ID of the Investor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="folio_number" type="String" %}
Folio number of the Investor
{% endswagger-parameter %}

{% swagger-response status="201: Created" description="Success" %}
```javascript
{
    "status": "success",
    "message": "Nominee has been successfully added"
    "wayneReferenceId": "*******************"
}
```
{% endswagger-response %}
{% endswagger %}
