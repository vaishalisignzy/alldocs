# Initiating Video Call

In this API, you will create the call in which the RE Agent and the end user will be connected together. It is a fully customisable flow which can be configured in this API.

{% swagger baseUrl="https://video-conf-demo.signzy.app" path="/scheduling/Customers/createCall" method="post" summary="Create a Call API" %}
{% swagger-description %}
To schedule a new call, the following request needs to be submitted with this API. 

\


In this request, you'll be required to send caller's data such as PAN ID photo with details, Aadhaar XML details etc.

\




\


You can also configure the entire video call flow such as having a customisable QnA during the video call, a feedback form for the RE after the call is ended etc. More details described below for each parameter. 

\




\




\


\============

\


1\. If you done have customer's access token, do a customer login to get one

\


2\. Create the call object, containing metaData and callData

\


3\. POST the request

\




\


For creation of call object, we need metaData and callData

\


metaData is used to specifiy the priority and type of call

\


properties of metaData:

\


1\. priority - true | false, if true, we treat as priority call else it is a non priority (boolean)

\


2\. scheduled - true | false, if true, we treat the call as a scheduled call, else live call

\




\


now moving on to callData, we have to make sure we have the customer config data with us, before hand. Customer config includes, all data like instructions to be displayed, what's the fields which are needed to be captured once the flow is completed for the admin, the generic configurations and all those things which are present in the customer panel.

\




\


To get the customer details, we need to consume the customer configuration request.

\




\


let say, customerData be the varaibel which has the customerConfig, now let's start creating the callData object

\




\


callData={}

\


callData.meetingName = "..Can be auto generated.."

\


callData.emailRequired = true | false //If you want the end user to recieve an email

\


calData.configuration = customerData.config.introConf

\


callData.languagesRequired = customerData.config.languagesOptions

\


callData.fields = customerData.config.fields

\


callData.callbackSystem = { 

\


"dataCallbackUrl": "...callback URL", 

\


"dataCallbackParameters": { "requestId": "...request ID..." }

\


}

\




\


Now, for callData.users, we need to create users block, It is basically an array, which accepts user objects, let us take 'userObj' as an userObj, and let's create it

\




\


userObj.documents = [ .. list of documents ..]

\




\


To create a document, we need 3 things, documentName, data, image. The documents basically belongs to an user.

\




\


let's take example of offline aadhaar, it has a image, and data.

\


so documentObject be :

\


{

\


"documentName":"Offline Aadhaar",

\


"image":"https://imagelink.com",

\


"data":{

\


"name":"Awesome name",

\


"dob":"Awesome date of birth"

\


}

\


}

\




\


so coming back to userObj, we have already added user documents, now let's move ahead for configuring it further.

\




\


userObj.instructions = customerData.config.instructions

\


userObj.name = ".. Name of user .."

\


userObj.email = ".. Email of user.." //This email will be used for sending user an email.

\




\


Now as we are done with adding the user infomration, let's put it back in the callData section

\




\


callData.users = [userObj]

\




\


Now we can hit the api with the customer token passed in header, to the undermentioned endpoint.

\




\



{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Customer's Access token
{% endswagger-parameter %}

{% swagger-parameter in="body" name="metaData" type="object" %}
Call's metadata, like priority preference, scheduling preference 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="callData" type="object" %}
Call Definition
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{ "requestId": "An auto generated ID for the call" }
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="Sample Request Body" %}
```javascript
{
    "metaData": {
        "priority": true
    },
    "callData": {
        "meetingName": "signzy ekyc conf",
        "backopsName": "name of the user",
        "backopsEmail": "email@useremail.com",
        "emailRequired": "false",
        "configuration": {
            "advideo": "https://www.youtube.com/embed/3louCp0pc-s",
            "consentText": "The consent that needs to be shown to the user"
        },
        "languagesRequired": [
            "HINDI",
            "KANNADA",
            "BENGALI",
            "GUJARATI"
        ],
        "users": [
            {
                "documents": [
                    {
                        "image": "image URL here",
                        "data": {
                            "dob": "data",
                            "name": "Name to be provided"
                        }
                    }
                ],
                "instructions": [
                    {
                        "text": "Please show PAN Card",
                        "isScreenshotRequired": true,
                        "isIDCardBoxRequired": true,
                        "isSideNavRequired": true
                    },
                    {
                        "text": "Please speak out your name",
                        "isIDCardBoxRequired": true,
                        "isScreenshotRequired": true,
                        "isSideNavRequired": false
                    },
                    {
                        "text": "Please speak out your Date of Birth",
                        "isScreenshotRequired": true,
                        "isIDCardBoxRequired": false,
                        "isSideNavRequired": true
                    }
                ],
                "randomizeInstructions": true,
                "name": "User Name",
                "email": "emailof@user.com"
            }
        ],
        "fields": [
            {
                "elementType": "inputField",
                "variable": "message",
                "placeHolder": "Message",
                "isRequired": true
            },
            {
                "elementType": "dropdown",
                "variable": "applicationStatus",
                "placeHolder": "Application Status",
                "isRequired": true,
                "options": [
                    "Accept",
                    "Reject",
                    "Redo"
                ]
            },
            {
                "elementType": "multiSelectDropdown",
                "variable": "rejectionReason",
                "placeHolder": "Application Rejection Criteria",
                "isRequired": true,
                "options": [
                    "PAN CARD NOT CLEAR",
                    "FACE DID NOT MATCH",
                    "INTERUPTED SERVICES"
                ]
            }
        ],
        "callbackSystem": {
            "dataCallbackUrl": "...callback URL",
            "dataCallbackParameters": {
                "requestId": "...request ID..."
            }
        }
    }
```
{% endtab %}
{% endtabs %}

## 1.1)  Request Body Description

| Property              | Data Type                                        | Description                                                                                                                                                                 |
| --------------------- | ------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| metaData              | Object (Required)                                | contains details of how the call will be handled                                                                                                                            |
| -- priority           | Boolean  (Optional)                              | whether its a priority call, defaults to false                                                                                                                              |
| callData              | Object (Required)                                | Description of video conference call                                                                                                                                        |
| -- meetingName        | String (Required)                                | A name for meeting                                                                                                                                                          |
| -- emailRequired      | Enum (Optional), values: "true", "false"         | whether conference details to be mailed to user                                                                                                                             |
| configuration         | Object (Required)                                |  some config for end user's welcome page                                                                                                                                    |
| -- advideo            | URL String (Required)                            | Video URL to be shown on welcome page                                                                                                                                       |
| -- consentText        | String (Optional)                                | Consent Text for user                                                                                                                                                       |
| languagesRequired     | Array of Strings ( Required )                    | Languages options using Google Translate, Allowed values: `"HINDI"`, `"KANNADA"`, `"BENGALI"`, `"GUJARATI"`, `"MALAYALAM"`, `"MARATHI"`, `"PUNJABI"`, `"TAMIL"`, `"TELUGU"` |
| users                 | Array of objects containing user Info (Required) | End user Info, See Table 1.2 for details                                                                                                                                    |
| fields                | Array of object containing field Info (Optional) | Form fields to be shown on VCIP admin's Interface at the end of conference, see Table 1.5                                                                                   |
| callbackSystem        | Object (Required)                                | contains callback URLs where our system can post data about the related conference call                                                                                     |
| -- dataCallbackUrl    | URL string (Optional)                            | a POST request is sent to this URL along with the results of the conference                                                                                                 |
| -- callbackParameters | Object (Optional)                                | this object may contain some identifying details, and will sent in the body of data posted to `dataCallbackUrl` , check   `callbackParameters`  property in the post body   |

### 1.2 User Properties

| Property     | Data Type                   | Description                                                                                                                    |
| ------------ | --------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| documents    | Array of objects (Required) | minimum of one document and a maximum of two documents are allowed in the array, contains user document details, see Table 1.3 |
| instructions | Array of objects (Required) | Sequence of instructions to be prompted in presenter's interface, see Table 1.4                                                |

### 1.3 Document Properties

| Property | Data Type             | Description                                   |
| -------- | --------------------- | --------------------------------------------- |
| image    | URL string (Required) | User's ID Card image                          |
| data     | Object (Optional)     | Contains any kind of text info about document |

### 1.4 Instruction Properties

| Property             | Data type          | Description                                           |
| -------------------- | ------------------ | ----------------------------------------------------- |
| text                 | String (Required)  | Instruction Text                                      |
| isScreenshotRequired | Boolean (Required) | whether screenshot required for this instruction step |
| isIDCardBoxRequired  | Boolean (Required) | Whether dotted bounding box is to be shown            |
| isSideNavRequired    | Boolean (Required) | whether side navigation to be shown                   |

### 1.5 Field Properties

| Property    | Data type                                                                                      | Description                                                                   |
| ----------- | ---------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| elementType | Enum (Required)                                                                                | Type of input, One of `dropdown, textArea, multiSelectDropdown,  inputField`  |
| variable    | String (Required)                                                                              | Name of the Variable                                                          |
| placeHolder | String (Required)                                                                              | Placeholder for input                                                         |
| isRequired  | Boolean (Required)                                                                             | whether field input is mandatory                                              |
| options     | Array of Strings (Required incase `elemetType` is either  `dropdown` or `multiSelectDropdown`) | option text to be shown in dropdown                                           |

##
