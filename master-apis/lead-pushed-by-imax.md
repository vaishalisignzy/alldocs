# Lead Pushed By Imax



This api is used to push lead from Imax (Lead Management System) to android application, these leads are then displayed on the "LEAD" tab of the RM dashboard on the application.

#### LMS1-Available HTTP Endpoints <a href="#lms1-available-http-endpoints" id="lms1-available-http-endpoints"></a>

* _Get all data_

**GET** : /utilities/leadPusheds

* _Find one_

**GET** : /utilities/leadPusheds/findOne

* _Find by id_

**GET** : /utilities/leadPusheds/{id}

* _Insert a lead_

**POST** : /utilities/leadPusheds

* _Update data of lead_

**POST** : /utilities/leadPusheds/update

* _Delete a lead_

**DELETE** : /utilities/leadPusheds/{id}

#### LMS1-Headers <a href="#lms1-headers" id="lms1-headers"></a>

| Property     | Value            |
| ------------ | ---------------- |
| Content-type | application/json |
| Accept       | application/json |

### LMS1-Available Properties <a href="#lms1-available-properties" id="lms1-available-properties"></a>

* customerName
* mobileNumber
* emailId
* lmsId
* rmCode

### LMS1-Get All Data <a href="#lms1-get-all-data" id="lms1-get-all-data"></a>

This API endpoint helps you retrieve all the data objects stored in database with their unique Ids.

URL : /utilities/leadPusheds

Method Type : GET

> Response JSON

```
[{
    "customerName": "string",
    "mobileNumber": "string",
    "emailId": "string",
    "lmsId": "string",
    "rmCode": "string",
    "id": "string"
}]
```

&#x20;You can also pass \`filter\` in query to get all instances matching particular properties.

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/leadPusheds?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}

### LMS1-Find first matching result <a href="#lms1-find-first-matching-result" id="lms1-find-first-matching-result"></a>

This API endpoint helps you retrieve first data object matching the given properties, pass the filter argument in query, please see example url.

URL : /utilities/leadPusheds/findOne

Method Type : GET

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/leadPusheds/findOne?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}
>
> Response JSON

```
{
    "customerName": "string",
    "mobileNumber": "string",
    "emailId": "string",
    "lmsId": "string",
    "rmCode": "string",
    "id": "string"
}
```

### LMS1-Find by id <a href="#lms1-find-by-id" id="lms1-find-by-id"></a>

This API endpoint helps you retrieve data object matching unique object id, just pass the id replacing _{id}_ in the endpoint.

URL : /utilities/leadPusheds/{id}

Method Type : GET

> Example URL : https://indusind-dev.signzy.tech/utilities/leadPusheds/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
    "customerName": "string",
    "mobileNumber": "string",
    "emailId": "string",
    "lmsId": "string",
    "rmCode": "string",
    "id": "string"
}
```

### LMS1-Insert a lead <a href="#lms1-insert-a-lead" id="lms1-insert-a-lead"></a>

This API endpoint lets you push lead into database, just hit the API with valid JSON object containing leads's data.

URL : /utilities/leadPusheds

Method Type : POST

> Request JSON

```
{
    "customerName": "string",
    "mobileNumber": "string",
    "emailId": "string",
    "lmsId": "string",
    "rmCode": "string"
}
```

> Response JSON

```
{
    "customerName": "string",
    "mobileNumber": "string",
    "emailId": "string",
    "lmsId": "string",
    "rmCode": "string",
    "id": "string"
}
```

### LMS1-Delete a lead <a href="#lms1-delete-a-lead" id="lms1-delete-a-lead"></a>

This API endpoint helps you delete data object matching unique object id, returns number of documents affected.

URL : /utilities/leadPusheds/{id}

Method Type : DELETE

> Example URL : https://indusind-dev.signzy.tech/utilities/leadPusheds/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
    "count": 1
}
```

### LMS1-Update data of lead <a href="#lms1-update-data-of-lead" id="lms1-update-data-of-lead"></a>

This API endpoint allows you to update all documents found by where filter with new values specified in body and returns number of documents modified.

URL : /utilities/leadPusheds/update

Method Type : POST

> Example URL with filter : https://indusind-dev.signzy.tech/utilities/leadPusheds/update?where={"property\_one": "value\_one","property\_two": "value\_two"}
>
> Request JSON

```
{
   "property_one" : " new_value"
  }
```

> Response JSON

```
{
    "count": 1
}
```
