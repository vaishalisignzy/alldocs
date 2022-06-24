# Check Enrollment Status of all Users

Check the enrollment status of all your users

{% swagger baseUrl="https://deepfaceauth.signzy.app/deepfaceauth" path="/api/v1/basic/status/enroll/all" method="post" summary="check enrollment status of all users" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
The Access Token for the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerName" type="string" %}
Customer Name was given to you by Signzy.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pageNumber" type="string" %}
Page Number
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pageCount" type="string" %}
Count in that page
{% endswagger-parameter %}

{% swagger-parameter in="body" name="statusType" type="string" %}
success | failure | draft
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fromThisDate" type="string" %}
yyyy-mm-dd hh:mm:ss
{% endswagger-parameter %}

{% swagger-parameter in="body" name="toThsiDate" type="string" %}
yyyy-mm-dd hh:mm:ss
{% endswagger-parameter %}

{% swagger-response status="200" description="application/json" %}
```
{
  "status": "200 OK",
  "message": "success"
  "currentStatusPageNumber": "...pagenumber.."
  "totalStatusPageNumber": "...totalpages..",
  "totalStatusEnrollmentCount": "...totalcount..",
  "data": [
    {
      "userName": "a unique User Name you had registered",
      "fullName": "the actual name of the user",
      "emailId": "the email id of the user",
      "phoneNumber": "the phone number of the user",
      "faceThumbnail": "Thumbnail face image of the user",
      "faceOriginal": "face image of the user",
      "timeStamp": "2019-06-04 18:17:40",
      "blacklistState": "no"
    }
  ]
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="Request Schema" %}
```
{
  "customerName": "...userName of the customer provided by Signzy...",
  "pageNumber": "1",
  "pageCount": "10",
  "statusType": "success",
  "fromThisDate": "2019-06-03 18:23:47",
  "toThisDate": "2019-06-04 18:17:40"
}
```
{% endtab %}

{% tab title="Response Parameters" %}
| Parameter Name             | Parameter  Type  | Parameter Description     |
| -------------------------- | ---------------- | ------------------------- |
| status                     | string           | status of the request     |
| message                    | string           | message for the user      |
| data                       | array of objects | The list of users         |
| currentStatusPageNumber    | Int              | Page number               |
| totalStatusPageNumber      | Int              | Total Pages               |
| totalStatusEnrollmentCount | Int              | Total Count of Enrollment |


{% endtab %}
{% endtabs %}

