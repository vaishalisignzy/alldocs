# View Settings

To access the settings of the system.

{% swagger baseUrl="https://deepfaceauth.signzy.app/deepfaceauth" path="/api/v1/basic/settings/view" method="post" summary="View settings" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Access Token for the User
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerName" type="string" %}
Customer Name provided by Signzy
{% endswagger-parameter %}

{% swagger-response status="200" description="application/json" %}
```
{
   "checkLiveliness": "yes/no",
   "Threshold": "..value..",
   "enrollmentAcceptedCallbackurl": "...callbackurl..",
   "enrollmentRejectedCallbackurl": "...callbackurl..",
   "otpccheckifScorebelowThreshold": "no/yes",
   "successfullAuthenticationCallbackurl": "..callbackurl..",
   "failedAuthenticationCallbackurl": "..callbackurl..",
   "enrollAcceptEmail": {
       "emailSubjectField": "Mail for Successful enrollment",
       "emailBodyField": "One of the user has enrolled",
       "emailFromField": "saravanan@signzy.com",
       "emailToField": []
   },
   "enrollRejectEmail": {
       "emailSubjectField": "Verification mail for UnSuccessful enrollment ",
       "emailBodyField": "One of the user tried to enroll but failed in process",
       "emailFromField": "himani.pathak@signzy.com",
       "emailToField": []
   },
   "sendEnrolledUrlEmail": {
       "emailSubjectField": "Please Find Your enrollment url",
       "emailBodyField": "Your enrollment Url is : ",
       "emailFromField": "himani.pathak@signzy.com",
       "emailToField": []
   },
   "sendEnrolledUrlSms": "Your face enrollment URL is :",
   "customerName":"Rama"
}
{
    "message": "success.",
    "status": "200 OK"
}
}
```
{% endswagger-response %}
{% endswagger %}
