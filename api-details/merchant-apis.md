# Merchant

### Create Merchant

#### Input headers <a href="#input-headers" id="input-headers"></a>

| Property      | Value                                     |
| ------------- | ----------------------------------------- |
| Content-type  | application/json                          |
| Authorisation | Authorization header as per login request |

```
{
  "email": "Merchant's valid Email-Id",
  "phone": "Merchant's valid Phone Number",
  "name": "Merchant's Name",
  "username": "Merchant's Username",
  "tagObject":{
    "key": "value"
  }
}
```

#### Input for Create Merchants <a href="#input-for-create-merchants" id="input-for-create-merchants"></a>

Post request to: **/engine/customers/:customerId/merchants/**

Below table describes all the properties available in the request body.

| Property  | Accepted values/format | Description                                                                  |
| --------- | ---------------------- | ---------------------------------------------------------------------------- |
| email     | Email (String)         | A valid email to represent the Merchant                                      |
| phone     | String                 | Phone number of the Merchant                                                 |
| name      | String                 | Name of the Merchant. This can be an individual's or an entity's name        |
| username  | String                 | A unique username for your Merchant                                          |
| tagObject | Object                 | This object can be used to specify key-value pairs to query the Merchants on |

**The tagObject should be created before using it in create Merchant. The create HashTag endpoint should be used.**

#### Expected Response <a href="#expected-response" id="expected-response"></a>

```
{
  "email": "Merchant's valid Email-Id",
  "phone": "Merchant's valid Phone Number",
  "name": "Merchant's Name",
  "username": "Merchant's Username",
  "tagObject": {
    "key": "value"
  },
  "id": "Merchant's id",
  "customerId": "Customer's id"
}
```

| Property   | Returned values/format | Description                                                                  |
| ---------- | ---------------------- | ---------------------------------------------------------------------------- |
| email      | Email (String)         | Email id that represents a Merchant                                          |
| phone      | String                 | Phone number of the Merchant                                                 |
| name       | String                 | Name of the Merchant.                                                        |
| username   | String                 | A unique username for your Merchant                                          |
| tagObject  | Object                 | This object can be used to specify key-value pairs to query the Merchants on |
| id         | String                 | An alphanumeric unique identifier for the Merchant                           |
| customerId | String                 | Id of the Customer, who the Merchant belongs to                              |

### Get Merchants

#### Input headers <a href="#input-headers-2" id="input-headers-2"></a>

| Property      | Value                                     |
| ------------- | ----------------------------------------- |
| Authorisation | Authorization header as per login request |

#### Input for Get Merchants <a href="#input-for-get-merchants" id="input-for-get-merchants"></a>

Get request to: **/engine/customers/:customerId/merchants/**

#### Expected Response <a href="#expected-response-2" id="expected-response-2"></a>

An array of all Merchants that belong to the Customer.

### Get Merchant by Id <a href="#get-merchant-by-id" id="get-merchant-by-id"></a>

#### Input headers <a href="#input-headers-3" id="input-headers-3"></a>

| Property      | Value                                     |
| ------------- | ----------------------------------------- |
| Authorisation | Authorization header as per login request |

#### Input for Get Merchants <a href="#input-for-get-merchants-2" id="input-for-get-merchants-2"></a>

Get request to: **/engine/customers/:customerId/merchants/:merchantId**

#### Expected Response <a href="#expected-response-3" id="expected-response-3"></a>

```
{
    "email": "Merchant's email",
    "phone": "Merchant's Phone Number",
    "name": "Merchant's Name",
    "username": "Merchant's Username",
    "id": "Merchant Id",
    "customerId": "Customer Id",
    "status": "pending/accepted/rejected",
    "tagLimit": "Number of tags that can be created by the Merchant",
    "documentLimit": "Number of documents that can be created by the Merchant",
    "grants": "Grant Object of the Merchant",
    "requestId": "Array of all requestIds collected from every time the verification engine is called"
}
```

### Merchant Login <a href="#merchant-login" id="merchant-login"></a>

#### Input Headers <a href="#input-headers-4" id="input-headers-4"></a>

| Property     | Value            |
| ------------ | ---------------- |
| Content-type | application/json |

```
{
  "username": "Merchant's username",
  "password": "Merchant Id"
}
```

#### Input for Merchant Login <a href="#input-for-merchant-login" id="input-for-merchant-login"></a>

Post request to: **/engine/merchants/login**

Below table describes all the properties available in the request body.

| Property | Accepted values/format | Description                                       |
| -------- | ---------------------- | ------------------------------------------------- |
| username | String                 | A unique username for your Merchant               |
| password | String                 | Merchant id returned from the create Merchant API |

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
| userId   | String                 | Merchant Id                                                                         |

### Create HashTag <a href="#create-hashtag" id="create-hashtag"></a>

#### Input headers <a href="#input-headers-5" id="input-headers-5"></a>

| Property      | Value                                     |
| ------------- | ----------------------------------------- |
| Content-type  | application/json                          |
| Authorisation | Authorization header as per login request |

```
{
  "name": "The key which will be specified in the tagObject in Create Merchant",
  "values": "Array of possible values for that key"
}
```

#### Input for Create Merchants <a href="#input-for-create-merchants-2" id="input-for-create-merchants-2"></a>

Post request to: **/engine/customers/:customerId/hashTags/**

Below table describes all the properties available in the request body.

| Property | Accepted values/format | Description                                                         |
| -------- | ---------------------- | ------------------------------------------------------------------- |
| name     | String                 | The key which will be specified in the tagObject in Create Merchant |
| values   | Array                  | Array of possible values for that key                               |

#### Expected Response <a href="#expected-response-4" id="expected-response-4"></a>

```
{
  "name": "The key which will be specified in the tagObject in Create Merchant",
  "values": "Array of possible values for that key",
  "id": "Merchant's id",
  "customerId": "Customer's id"
}
```

| Property   | Returned values/format | Description                                                         |
| ---------- | ---------------------- | ------------------------------------------------------------------- |
| name       | String                 | The key which will be specified in the tagObject in Create Merchant |
| values     | Array                  | Array of possible values for that key                               |
| id         | String                 | An alphanumeric unique identifier for the Merchant                  |
| customerId | String                 | Id of the Customer, who the Merchant belongs to                     |
