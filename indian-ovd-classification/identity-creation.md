# Identity Creation

### The entire identity workflow consists of the following stages.: <a href="#the-entire-identity-workflow-consists-of-the-following-stages" id="the-entire-identity-workflow-consists-of-the-following-stages"></a>

* Auto read (Extraction) - This is used to extract the information from the image of the ID card.
* Data Verification - This is done to check data consistency and authenticity.
* Data Fetch - This is used to extract the information from the identity number.

This document is designed to illustrate a clear idea of how the Identity APIs work.

You can use the navigation on the left to walk through each ID-card and the processes involved.

&#x20;Now let us talk about the various stages of the workflow in depth:

#### Auto reading  <a href="#auto-reading" id="auto-reading"></a>

Auto reading is done to save users from the trouble of manually entering values each and every data field. This API reads the fields mentioned on an ID card. The API accepts image(s) of Identity cards and returns the fields it could read from them.

You could pre-fill the form fields using the auto read output and ensure that user does not have to type all the information from his card. The autofilled data can then be validated to make sure any mistakes that might have crept in from the machine reading are removed before sending it for verification.

#### Data verification  <a href="#data-verification" id="data-verification"></a>

Once the data from the ID card has been extracted, the data has to be checked for correct entries or in other words, the data needs to be validated. The verification step should be executed once the data has been validated for correctness. The input data is further checked against government and other trusted ledgers for validity of information. The API returns with true/false indicating the input information is correct.

#### Data fetch  <a href="#data-fetch" id="data-fetch"></a>

Data fetch is used to extract a person's details from the identity number. The input data is searched in government and other trusted ledgers for validity of information. The API returns information on the identity number.

#### Task parameters & Snoop requests <a href="#task-parameters-and-snoop-requests" id="task-parameters-and-snoop-requests"></a>

After you create an Identity object as described in the following section, you can perform the following tasks in the name of snoop requests.

* autoRecognition
* verification
* fetch

### Creating an Identity card object  <a href="#creating-an-identity-card-object" id="creating-an-identity-card-object"></a>

The purpose of creating an identity card object is to ensure that the API can easily identify and utilise the data fields provided in the ID card before performing any auto recognition, verification or fetch, you need to create an Identity object. All operations related to a particular ID card are executed through this object.

&#x20;Creating an Identity object will require you to be logged in using the username and API-key. To know how to authenticate visit the Authentication section.

&#x20;The following is a list of parameters which are supported for creation of Identity objects :

* individualPan
* businessPan
* aadhaar
* passport
* drivingLicence
* cheque

​

#### Creating Identity object:  <a href="#creating-identity-object" id="creating-identity-object"></a>

#### The following example demonstrates creation of an Identity object for verifying an 'individualPan':Creating Identity object:&#xD; <a href="#the-following-example-demonstrates-creation-of-an-identity-object-for-verifying-an-individualpan" id="the-following-example-demonstrates-creation-of-an-identity-object-for-verifying-an-individualpan"></a>

#### The following example demonstrates creation of an Identity object for verifying an 'individualPan':

{% swagger baseUrl="https://preproduction.signzy.tech" path="/api/v2/patrons/<patron-id>/identities" method="post" summary="Identity Object" %}
{% swagger-description %}
**Production URL:**

\




`https://signzy.tech/api/v2/patrons/<patron-id>/identities`

\




\


This method allows the creation of identity object.
{% endswagger-description %}

{% swagger-parameter in="header" name="Content-type" type="string" %}
Application/JSON
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
Contains the id parameter returned from the login step
{% endswagger-parameter %}

{% swagger-parameter in="body" name="callbackURL" type="string" %}
This parameter for posting data if it is required to post the post data to some other URL for the particular request
{% endswagger-parameter %}

{% swagger-parameter in="body" name="images" type="string" %}
Contains the URLs of the uploaded images
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" type="string" %}
Email-Id of the user
{% endswagger-parameter %}

{% swagger-parameter in="body" name="type" type="string" %}
Type of ID card. Supported Types: individualPan, businessPan, aadhaar, passport, cheque, drivingLicence
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
	"type": "individualPan",
	"email": "admin@signzy.com",
	"callbackUrl": "https://your-domain.com/your-callback-system",
	"images": [
		"<urls-to-uploaded-files>"
	],
	"autoRecognition": [],
	"verification": [],
	"forgeryCheck": [],
	"accessToken": "..access-token-for-the-snoop-request..",
	"id": "..itemId-for-the-snoop-request....",
	"patronId": "..your-id-into-signzy-system-(userId-returned-from-the-login-call).."
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="Request Schema" %}
```
 {
  "type": "individualPan",
  "email": "admin@signzy.com",
  "callbackUrl": "https://your-domain.com/your-callback-system",
  "images": [
   "<urls-to-uploaded-files>"
  ]
}
```
{% endtab %}

{% tab title="Response Parameter" %}
| Parameter Name  | Description                                                    |
| --------------- | -------------------------------------------------------------- |
| autoRecognition | Used for identifying the document                              |
| verification    | Used for verifying the document                                |
| accessToken     | Access token for the snoop request                             |
| id              | item id for the snoop request                                  |
| patronId        | The id for Signzy system that is returned from the login call. |
{% endtab %}
{% endtabs %}



### &#x20; <a href="#identity-object" id="identity-object"></a>
