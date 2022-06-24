---
description: To change the setting of the system
---

# Change Settings

{% swagger baseUrl="https://deepfaceauth.signzy.app/deepfaceauth/api" path="/v1/basic/settings/change" method="post" summary="Change Settings" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="" type="string" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="checkLiveliness" type="string" %}
yes/no
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Threshold" type="string" %}
Dropdown value from 10 to 90 in the range of 10
{% endswagger-parameter %}

{% swagger-parameter in="body" name="enrollmentAcceptedCallbackurl" type="string" %}
URL
{% endswagger-parameter %}

{% swagger-parameter in="body" name="enrollmentRejectedCallbackurl" type="string" %}
URL
{% endswagger-parameter %}

{% swagger-parameter in="body" name="otpccheckifScorebelowThreshold" type="string" %}
yes/no
{% endswagger-parameter %}

{% swagger-parameter in="body" name="successfullAuthenticationCallbackurl" type="string" %}
URL
{% endswagger-parameter %}

{% swagger-parameter in="body" name="failedAuthenticationCallbackurl" type="string" %}
URL
{% endswagger-parameter %}

{% swagger-parameter in="body" name="enrollAcceptEmail" type="object" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="enrollRejectEmail" type="object" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="sendEnrolledUrlEmail" type="object" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="sendEnrolledUrlSms" type="string" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerName" type="string" %}
Name given to you by Signzy
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "message": "Successfully Updated.",
    "status": "200 OK"
}
```
{% endswagger-response %}
{% endswagger %}
