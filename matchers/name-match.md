# Name Match

### Creating a request for Name Match

The Name Match product takes two names input and returns a match result of two names. This ensures authenticity of the name. Before conducting a name match, users need to login after which a search request can be sent.&#x20;

The users are required to pass the access token received from the login call as the authorization header in the Name Match request.

The following exchange parameters can be used for conducting a Name Match:

{% swagger baseUrl="https://preproduction.signzy.tech" path="/api/v2/patrons/...patronID.../matchers" method="post" summary="Name Match" %}
{% swagger-description %}
Production URL:

\




`https://signzy.tech/api/v2/patrons/...patronID.../matchers`

\


This method matches the entered two names
{% endswagger-description %}

{% swagger-parameter in="header" name="Content-type" type="string" %}
Application/JSON
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Contains the access token which is returned as id field of login request.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="essentials.nameBlock" type="string" %}
Contains the two names which are to be compared for a successful name match.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="essentials" type="string" %}
Contains the essential input data
{% endswagger-parameter %}

{% swagger-parameter in="body" name="task " type="string" %}
The task to be performed - name Match
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "result": {
        "name1_vs_name2_matchResult": "Direct Match/Partial Match/No Match",
        "name1_vs_name2_matchScore": "...score between 0 and 1",
        "name1_vs_name2_matchReason": "...match reason..."
    }
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="Request Schema" %}
```
 {

   "task": "nameMatch",
   "essentials": {
     "nameBlock" : {
         "name1" : "...name1...",
         "name2" : "...name2..."
     }
```
{% endtab %}

{% tab title="Response Parameter" %}
| Parameter Name  | Description                                |
| --------------- | ------------------------------------------ |
| result          | Contains the output of the given request.  |
| matchResult     | Direct Match/Partial Match/No Match        |
| matchScore      | Match Score between 0 and 1                |
| matchReason     | Match Reason                               |
{% endtab %}
{% endtabs %}

