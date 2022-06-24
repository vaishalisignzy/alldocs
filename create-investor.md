---
description: >-
  The Api is used for creating investors for customer that need to be onboarded.
  For that we need to have hostname and protocol which are as defined in
  Authentication section
---

# Create Investor

### Sending requests <a href="#sending-requests" id="sending-requests"></a>

For sending request the hostname and protocol will be same as given in [Authentication](https://docs-investor-onboarding.signzy.tech/#authentication) section.

Send a post request to: **/api/customers/:customer-id/merchants** with data as below.

#### Headers <a href="#headers" id="headers"></a>

| Property      | Value                                         |
| ------------- | --------------------------------------------- |
| Content-type  | application/json                              |
| Authorization | Authorisation header as per the login request |

#### Request Body <a href="#request-body" id="request-body"></a>

```
{
  "name" : "...name...",    
  "email": "...email...",
  "username":"...username...",
  "phone" : "...phone....",
  "redirectUrl" : "...redirectUrl..."
}
```

Below table describes all the properties available in the request body.

| Property              | Accepted values/format | Description                                                                                                                                                                       |
| --------------------- | ---------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| name                  | String                 | Name for the end user whose onboarding needs to be conducted                                                                                                                      |
| email                 | Email (String)         | Email for the end user whose onboarding needs to be conducted                                                                                                                     |
| username              | String                 | Username of the end user (needs to be provided for them to be able to login) (Username should be Lower Case and allowable characters alphanumeric and special characters (.\_ .)) |
| phone                 | String                 | Phone for the end user whose onboarding needs to be conducted                                                                                                                     |
| redirectUrl(optional) | String                 | Merchant will redirect to the redirectURL after the onboarding gets completed or if he/she clicks on the logout button.                                                           |

### Expected Create Investor Response <a href="#expected-create-investor-response" id="expected-create-investor-response"></a>

```
{
    "email": ".... email ....",
    "phone": ".... phone ....",
    "username": ".... username ....",
    "id": ".... id ....",
    "customerId": ".... customerId ....",
    "applicationUrl": ".... applicationUrl ....",
    "autoLoginUrL": ".... autoLoginUrL ....",
    "mobileLoginUrl": ".... mobileLoginUrl ....",
    "mobileAutoLoginUrl": ".... mobileAutoLoginUrl ...."
}
```

The below table describes the properties that are returned in the request.

| Property           | Accepted values/format | Description                                                                                        |
| ------------------ | ---------------------- | -------------------------------------------------------------------------------------------------- |
| email              | String                 | Email for the end user whose onboarding needs to be conducted                                      |
| phone              | String                 | Phone for the end user whose onboarding needs to be conducted                                      |
| username           | String                 | Username used to create that particular investor                                                   |
| id                 | String                 | merchantId(Id for investor) defined for this particular onboarding corresponding to above username |
| customerId         | String                 | customerId is the client ID whose login was used to create the investor                            |
| applicationUrl     | String                 | URL where to redirect the user for onboarding                                                      |
| autoLoginUrL       | String                 | URL where to redirect the user for onboarding without logging in                                   |
| mobileLoginUrl     | String                 | URL where to redirect the user for onboarding on mobile                                            |
| mobileAutoLoginUrl | String                 | URL where to redirect the user for onboarding on mobile without investorlogin                      |

Login Url and Mobile Login Url is used to redirect investorto the login page where they will give username and passowrd for getting logged in either desktop or mobile.

The " Auto Login Url " to open an iFrame within your application for the user to onboard without leaving your app.
