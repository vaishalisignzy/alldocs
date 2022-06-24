# Search face

This endpoint will be used to search for a user via his face in the system.&#x20;

{% swagger baseUrl="https://deepfaceauth.signzy.app/deepfaceauth" path="/api/v1/basic/search" method="post" summary="search" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Access Token of the user
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="body" name="customerName" type="string" %}
Customer Name which was given to you by Signzy.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="url" type="string" %}
image or video URL containing a face. 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="searchSpaces" type="string" %}
Set of users created in a search space. If no search space created then keep it null
{% endswagger-parameter %}

{% swagger-parameter in="body" name="threshold" type="string" %}
The recommended value is 0.5 
{% endswagger-parameter %}

{% swagger-response status="200" description="application/json" %}
```
{
    "faceOriginal": "..url..",
    "faceThumbnail": "..url..",
    "userNames": [
        {
            "userName": "..username..",
            "matchScore": value,
            "blacklistState": "..status.."
        }
    ],
    "message": "done",
    "status": 200
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="Request Schema" %}
```
{
                            
  "url": "..faceurl..",
  "threshold": "0.5",
  "customerName": "..customername..",
  "searchSpaces": null
}
```


{% endtab %}

{% tab title="Response Parameter" %}
| Parameter Name           | Parameter Type   | Parameter Description                                     |
| ------------------------ | ---------------- | --------------------------------------------------------- |
| status                   | string           | status of the request                                     |
| message                  | string           | message to the user                                       |
| userNames                | Array of Objects | top username matching with the face in the video \| image |
| userNames.userName       | string           | Username of the user                                      |
| userNames.matchScore     | string           | Match Score                                               |
| userNames.blacklistState | string           | yes/no                                                    |
| faceThumbnail            | string           | Zoomed face of the user                                   |
| faceOriginal             | string           | Original Image of the face                                |


{% endtab %}
{% endtabs %}

