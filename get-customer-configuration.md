---
description: >-
  This is the api which can be used to get the customer configuration. this is
  basically used while creating a call
---

# Get Customer Configuration

We can consume this api, by hitting an authenticated GET request by passing the auth token, and the customer id. Both the data can be obtained when done the customer login. "

{% swagger baseUrl="https://video-conf-demo.signzy.app" path="/scheduling/Customers/{{customerId}}" method="get" summary="Get customer configuration" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="customerId" type="string" %}
This will be the customer Id
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "username": "signzy_testing5b23a59e5c0ae906549bd9b5",
  "email": "signzy@sdkdf.cos",
  "id": "5e3ec49a7158790e1c04f294",
  "name": "5b23a59e5c0ae906549bd9b5",
  "config": {
    "instructions": [
      {
        "isIDCardBoxRequired": true,
        "isSideNavRequired": true,
        "isScreenshotRequired": true,
        "text": "Please Show your Pan Card?",
        "isInstructionPopupRequired": false,
        "automate": false,
        "waitTime": "10",
        "isTalkBack": true,
        "isFaceMatchRequired": true
      },
      {
        "isIDCardBoxRequired": false,
        "isSideNavRequired": true,
        "isScreenshotRequired": true,
        "text": "What is your Name?",
        "isOTPInstuction": false,
        "automate": false,
        "waitTime": "10",
        "isFaceMatchRequired": false
      },
      {
        "isIDCardBoxRequired": false,
        "isSideNavRequired": true,
        "isScreenshotRequired": false,
        "text": "Please speak out {{OTP}}",
        "isOTPInstuction": true,
        "isTalkBack": true,
        "automate": false,
        "waitTime": "10",
        "isFaceMatchRequired": false
      }
    ],
    "fields": [
      {
        "elementType": "dropdown",
        "variable": "Remark",
        "placeHolder": "Remark",
        "options": [
          "Good To Go",
          "Accepted",
          "Rejected"
        ],
        "isRequired": false,
        "conditionalRendering": false,
        "conditionalRenderingConditions": {}
      },
      {
        "elementType": "multiSelectDropdown",
        "isRequired": false,
        "conditionalRendering": true,
        "variable": "ItemsToSelect",
        "placeHolder": "selection",
        "options": [
          "POI Not Clear",
          "Internet Slow",
          "Recheck Required"
        ],
        "conditionalRenderingConditions": {
          "variable": "Remark",
          "data": "Rejected"
        }
      },
      {
        "elementType": "textarea",
        "isRequired": false,
        "conditionalRendering": false,
        "variable": "notes",
        "placeHolder": "Please give your notes."
      }
    ],
    "callPriority": {
      "LIVE_PRIORITY": 4,
      "LIVE_NONPRIORITY": 3,
      "SCHEDULED_PRIORITY": 4,
      "SCHEDULED_NONPRIORITY": 2
    },
    "languagesOptions": [
      "HINDI",
      "KANNADA",
      "BENGALI",
      "GUJARATI"
    ],
    "skillSets": [
      "ca",
      "mf"
    ],
    "introConf": {
      "advideo": "https://www.youtube.com/embed/6VfkW3QXCq8",
      "consentText": "Make sure you are suitably qualified to take informed consent for this particular procedure.",
      "instructionHeader": "Instructions to be followed during V-CIP process",
      "consentRequired": true,
      "isThankYouRequired": false,
      "isAppbar": false,
      "showETA": true,
      "averageETA": "5",
      "idleTimeRequired": true,
      "idleTime": "10",
      "allowUserToTurnOffCamera": true,
      "rescheduleConsent": "60",
      "isVideoConference": true,
      "isVideoKYC": false,
      "adminCallTimeoutDuration": "50",
      "isScreenshare": true,
      "isRecording": true
    },
    "conference": {
      "isScreenshare": true,
      "isRecording": true
    }
  },
  "isVideoConference": true,
  "isVideoKYC": true,
  "isScreenshare": true,
  "isRecording": true,
  "otpEmail": true,
  "otpSms": true
}
```
{% endswagger-response %}
{% endswagger %}
