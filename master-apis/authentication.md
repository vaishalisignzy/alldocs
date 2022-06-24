# Authentication

All the calls to Master APIs are authenticated using token based BASIC authentication, in which you need to pass on the token in every request. The token is checked for validity and the request is processed only when the token is found to be genuine. Otherwise the API returns a _401 Unauthorised response._

### Generating authorization token <a href="#generating-authorization-token" id="generating-authorization-token"></a>

To generate the Authorisation header to use with Basic authentication, you simply base64 encode the username and password separated by a colon.

For example if the username and password provided to you are '**shiv**' and '**shankar** respectively'. You will need to follow the below steps to generate the authentication header.

1. Create the string: 'shiv:shankar'
2. Base64 encode the string to get 'c2hpdjpzaGFua2Fy'
3. Prepend 'Basic ' to the string to get '**Basic c2hpdjpzaGFua2Fy**'. Now you will avail a string similar to the bold string which needs to be passed into the authentication header.

### Sending authenticated requests <a href="#sending-authenticated-requests" id="sending-authenticated-requests"></a>

Once you have an access token generated above, you can send further calls to different endpoints by passing the token in the **Authorization header**.

Anybody with your username/password or an Access Token string generated using them can access the APIs and send requests on your behalf. It is strongly recommended to not send username/Password to client side and instead use reverse proxy to call Master APIs.
