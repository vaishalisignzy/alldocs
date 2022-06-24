---
description: >-
  Logs of all transactions i.e. enrollment, face update, authenticate, search
  etc..
---

# Logs

### View logs

View Logs means to view all the transactions made by the users.

{% swagger baseUrl="https://deepfaceauth.signzy.app/deepfaceauth" path="/api/v1/basic/view/logs/all" method="post" summary="logs" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Access Token of the User
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerName" type="string" %}
Customer Name was given to you by Signzy.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pageNumber" type="string" %}
the page number you want to view.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pageCount" type="string" %}
the number of rows on a particular page.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fromThisDate" type="string" %}
yyyy-mm-dd hh:mm:ss
{% endswagger-parameter %}

{% swagger-parameter in="body" name="toThisDate" type="string" %}
yyyy-mm-dd hh:mm:ss
{% endswagger-parameter %}

{% swagger-response status="200" description="application/json" %}
```
{
    "currentPageNumber": 1,
    "totalPageNumber": 8,
    "totalLogCount": 40,
    "data": [
        {
            "timeStamp": "2020-11-12 18:32:37",
            "userName": "..username..",
            "fullName": "..fullname..",
            "emailId": "..emailid..",
            "phoneNumber": "..number..",
            "faceThumbnail": "..url..",
            "faceOriginal": "...url..",
            "requestType": "faceUpdate/enroll/authenticate/search",
            "videoUrl": "..url.."
        }
    ],
    "message": "success.",
    "status": "200 OK"
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="Request Schema" %}
```
{
  "customerName": "...userName of the customer provided by Signzy..."
  "pageNumber": "1",
  "pageCount": "10",
  "fromThisDate": "2019-06-03 18:23:47",
  "toThisDate": "2019-06-04 18:17:40"
}
```
{% endtab %}

{% tab title="Response Parameter" %}
| Parameter Name    | Parameter Type   | Parameter Description                                                 |
| ----------------- | ---------------- | --------------------------------------------------------------------- |
| status            | string           | Status of the request                                                 |
| message           | string           | Message for the User                                                  |
| data              | array of objects | This consists of a username, face URL, etc                            |
| currentPageNumber | Integer          | Current Page Number you want to look at                               |
| totalPageNumber   | Integer          | The total page number you want to see. This is in the range of 5-100. |
| totalLogCount     | Integer          | Total number of entries overall                                       |


{% endtab %}
{% endtabs %}

