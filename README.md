---
description: API documentation for custom XML endpoint
---

# ROC consolidated API



![](https://lh3.googleusercontent.com/ofesnknnxVzEMi9pNnRYRzRs9QbxZloNcKFGc4ga1wCuzM5Cce5u7NCJ7NpLkEn0ynDQ-Z-nM2xWw7K7HrV5Wz4JvmpIUJkk9IjE9wvs3D29rIKcuG7I3bZugMrqvmXxAR2VJgvJ)

## **Basic details:**

### **Pre-production**

**Protocol:** HTTPs\
**IP:** 13.234.24.101\
**Port:** 443\
**Host name:** blender-preproduction.signzy.app

### **Production**

**Protocol:** HTTPS\
**IP:** 13.234.24.101\
**Port:** 443\
**Host name:** blender.signzy.app

**API request & Response**

### **Authentication (Patron login)**

You need to have an access token for making any further API calls, which you can receive by logging in manually or programmatically  using these credentials.

Signzy APIs adhere to authentication defined by Swagger 2.0 specifications. Each call to the APIs should include an 'Authorization' header or 'access\_token' query parameter for authentication.

You can find working examples at the bottom of this page.

Logging in into the API service requires a simple HTTP call. Following section mentions data to be input, expected output and meaning of fields.

#### **Request**

**URL for test (pre production) Credentials**\
**POST :** [https://blender-preproduction.signzy.app/api/experian/login](https://blender-preproduction.signzy.app/api/experian/login)****\
****

**URL for live (production) credentials**\
**POST :** [https://blender.signzy.app/api/experian/login](https://blender.signzy.app/api/experian/login)****\
****

| Input JSON Body | <p><strong></strong><br><strong>{</strong><br>    <strong>"username": "..username..",</strong><br>    <strong>"password": "..password.."</strong><br><strong>}</strong></p> |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

#### ****

| **Expected response** | <p><strong>&#x3C;result></strong><br>    <strong>&#x3C;id>BlPDjeEc0Vm9zZdC0UNWO26lf0y0ULpmDGPPJl88isPlbcAyCFtD8ug1MFVxrHUF&#x3C;/id></strong><br>    <strong>&#x3C;ttl>31556926&#x3C;/ttl></strong><br>    <strong>&#x3C;created>2020-03-13T17:38:05.392Z&#x3C;/created></strong><br>    <strong>&#x3C;userId>5a905edq237c1a69414319d8&#x3C;/userId></strong><br><strong>&#x3C;/result></strong><br><strong></strong></p> |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

**Response properties are detailed as below**

1. id => your access token for accessing Signzy APIs
2. userId => your user ID as on file
3. ttl => number of seconds for which the access token is valid

#### **Sending authenticated requests**

Once you have an access token from the login API call, you can send further calls to different endpoints by passing the access-token in Authorization header or in access\_token query (GET) parameter.

It is advisable to send Access Token in header since query parameters are sometimes saved in the log files thereby exposing vulnerabilities until the access\_token is deleted from sessions.

#### **Security**

Anybody with your API key/password or an Access Token generated using them can access all information you have created and also send requests on your behalf. It is strongly recommended to not send API-key/Password to client side and instead use reverse proxy to call Signzy APIs.

If you think an access token is compromised, you should delete it using logout. Let us know if your Signzy Password/API-key is compromised as soon as possible, so that we can disable & create new ones and prevent any misuse of your data.\
****

### **Fetch company consolidated**

#### **Request**

#### **Expected Response**

### **Get company consolidated data**

#### **Request**

#### **Expected Response** 

### **Server level errors**

In case server crashes or non-existent endpoints are called for, Signzy API returns standard HTTP error codes. Below table describes the error codes (HTTP Response Status Codes) that can be received and what each of them mean.\
****

| **CODE** | **TITLE**                  | **DESCRIPTION**                                                                                                                                                                                          |
| -------- | -------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **200**  | **OK**                     | **The request was successful.**                                                                                                                                                                          |
| **204**  | **Not Modified**           | **There was no new data to return.**                                                                                                                                                                     |
| **304**  | **No Content**             | **Successfully Logged Out.**                                                                                                                                                                             |
| **400**  | **Bad Request**            | **The request was invalid or cannot be otherwise served. This may happen due to invalid Parameters passed.**                                                                                             |
| **401**  | **Authorization Required** | **Missing or incorrect authentication credentials.**                                                                                                                                                     |
| **403**  | **Access Forbidden**       | **The request is understood, but it has been refused or access is not allowed. An accompanying error message will explain why. This code is used when requests are being denied due to request limits.** |
| **404**  | **Not Found**              | **The URI requested is invalid or the resource requested is not available.**                                                                                                                             |
| **422**  | **Unprocessable Entity**   | **Missing Inputs or the JSON body of a request is badly-formed.**                                                                                                                                        |
| **500**  | **Internal Server Error**  | **Something is broken. This is usually a temporary error, for example in a high load situation or if an endpoint is temporarily having issues.Try again later..**                                        |
| **502**  | **Internal Server Error**  | **Signzy is down, or being upgraded.**                                                                                                                                                                   |
| **504**  | **Gateway Timeout**        | **The Signzy servers are up, but the request couldn’t be serviced due to some failure within the internal stack. Try again later..**                                                                     |
