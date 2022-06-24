# Authentication

### Authorizing your access <a href="#authorizing-your-access" id="authorizing-your-access"></a>

Username and API key act like your key to the APIs. You need to have an access token for making any further API calls, which you can receive by logging in manually or programmatically using these credentials.

Signzy APIs adhere to authentication defined by Swagger 2.0 specifications. Each further call to the APIs should include an 'Authorization' header or 'access\_token' query parameter for authentication.

### Logging in <a href="#logging-in" id="logging-in"></a>

Logging in into the API service password requires a simple HTTP call. Following section mentions data to be input, expected output and meaning of fields.

**Input to login request**

```
POST :: https://stripe-poc-prod.signzy.tech/api/patrons/login
Input
  {
    "username": "enter your valid username",
    "password": "enter your valid password"
  }
```

**Expected response**

```
{
    "id": "XXXXXXXX9FGZ5JXLVC4tYCvIE1Az8dnkFz3DWJ",
    "ttl": 1209600,
    "created": "2017-06-23T11:10:08.534Z",
    "userId": "594bda31fvdXXXX344baefa"
}

// id => your access token for accessing Signzy APIs
// userId => your user ID (patronId) as on file
// ttl => number of seconds for which the access token is valid

```

### Sending authenticated requests <a href="#sending-authenticated-requests" id="sending-authenticated-requests"></a>

Once you have an access token from the login API call, you can send further calls to different endpoints by passing the access-token in Authorization header or in access\_token query (GET) parameter.

It is advisable to send Access Token in header since, query parameters are sometimes saved in the log files thereby exposing vulnerabilities until the access\_token is deleted from sessions. Security

Anybody with your API key/password or an Access Token generated using them can access all information you have created and also send requests on behalf of you. It is strongly recommended to not send API-key/Password to client side and instead use reverse proxy to call Signzy APIs.

If case you think an access token is compromised, you should delete it using logout. Let us know if your Signzy Password/API-key is compromised as soon as possible, so that we can disable & create new ones and prevent any misuse of your data.

### Logging out <a href="#logging-out" id="logging-out"></a>

To logout you simply need to call the logout route with the access token in 'access\_token' query parameter or as 'Authorization' header.

```

POST :: https://stripe-poc-prod.signzy.tech/api/patrons/logout?access_token=:access-token-to-delete

// Response is 204 status code with no content, indicating the Access-token has been deleted.

```

