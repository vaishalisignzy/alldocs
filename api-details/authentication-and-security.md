# Authentication

### API Hostname & server IPs

**Protocol:** https

**Pre-Production-Hostname:** onboarding-engine-preproduction.signzy.tech

**URL:** As per each API endpoint

### Authorizing your access <a href="#authorizing-your-access" id="authorizing-your-access"></a>

You have a username and an API key. The key also acts like your password to the APIs. You need to have an access token for making any further API calls, which you can receive by logging in manually or programmatically using these credentials.

Signzy APIs adhere to authentication defined by Swagger 2.0 specifications. Each call to the APIs should include an 'Authorization' header or 'access\_token' query parameter for authentication.

### Logging in <a href="#logging-in" id="logging-in"></a>

For using Signzy APIs you have to first Login into Signzy System which is a simple Rest API(HTTPS) call with JSON parameters as username and password. Following section mentions the data to be input, expected output and meaning of fields in JSON.

#### Input headers <a href="#input-headers" id="input-headers"></a>

| Property     | Value            |
| ------------ | ---------------- |
| Content-type | application/json |

#### Input to login request <a href="#input-to-login-request" id="input-to-login-request"></a>

```
{
    "username": "enter your valid username",
    "password": "enter your valid password"
}
```

Post request to: **/engine/customers/login**

#### Expected Login response <a href="#expected-login-response" id="expected-login-response"></a>

```
{
    "id": "..id..",
    "ttl": "..ttl..",
    "created": "..created..",
    "userId": "..userId.."
}
```

| Property | Accepted values/format | Description                                                                         |
| -------- | ---------------------- | ----------------------------------------------------------------------------------- |
| id       | String                 | This is your access token to be passed into other endpoints as Authorization header |
| ttl      | Integer                | Time to live (ttl for the access token that is generated)                           |
| created  | String                 | Time and Date of creation of access-token                                           |
| userId   | String                 | ID of the customer which is the onboarding product's client                         |

### Sending authenticated requests <a href="#sending-authenticated-requests" id="sending-authenticated-requests"></a>

Once you have an access token from the login API call, you can send further calls to different endpoints by passing the access-token in Authorization header or in access\_token query (GET) parameter.

It is advisable to send Access Token in header. Since, query parameters are sometimes saved in the log files thereby exposing vulnerabilities until the access\_token is deleted from sessions.

### Logging out <a href="#logging-out" id="logging-out"></a>

To logout you simply need to call the logout route with the access token in 'access\_token' query parameter or as 'Authorization' header.

POST request to: **/engine/customers/logout?access\_token=:access-token-to-delete**

Response is 204 status code with no content, indicating the Access-token has been deleted.

### Security <a href="#security" id="security"></a>

#### Data transaction <a href="#data-transaction" id="data-transaction"></a>

We accept only secure HTTPS calls for all APIs, which adhere to strong cipher suite defined using SHA-256 with RSA Encryption. All transactional data are encrypted at the source and encryption is maintained throughout, so that there is no unauthorized access.

The urls expire in 30 seconds by default, unless explicitly specified in the inboud request in the ttl parameter.

#### Access Tokens & API keys <a href="#access-tokens-amp-api-keys" id="access-tokens-amp-api-keys"></a>

Anybody with your API key/password or an Access Token generated using them can access all information you have created and also send requests on your behalf. Hence it is strongly recommended not to send the API-key/Password to client side, instead use reverse proxy to call Signzy APIs.

You can disable any active access\_token by logging out. Let us know if your Signzy Password/API-key is compromised as soon as possible, so that we can disable & create new ones and prevent any misuse of your data.\
