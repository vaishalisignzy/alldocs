# Master Of RM



This master is used to create database for relationship managers, containing their basic information.

#### BM6-Available HTTP Endpoints <a href="#bm6-available-http-endpoints" id="bm6-available-http-endpoints"></a>

* _Get all data_

**GET** : /utilities/masterOfRms

* _Find one_

**GET** : /utilities/masterOfRms/findOne

* _Find by id_

**GET** : /utilities/masterOfRms/{id}

* _Insert data into master_

**POST** : /utilities/masterOfRms

* _Update data into master_

**POST** : /utilities/masterOfRms/update

* _Delete data from master_

**DELETE** : /utilities/masterOfRms/{id}

#### BM6-Headers <a href="#bm6-headers" id="bm6-headers"></a>

| Property     | Value            |
| ------------ | ---------------- |
| Content-type | application/json |
| Accept       | application/json |

### BM6-Available Properties <a href="#bm6-available-properties" id="bm6-available-properties"></a>

* rmCode
* rmName
* mobileNumber
* emailId

### BM6-Get All Data <a href="#bm6-get-all-data" id="bm6-get-all-data"></a>

This API endpoint helps you retrieve all the data objects stored in database with their unique Ids.

URL : /utilities/masterOfRms

Method Type : GET

> Response JSON

```
[{
    "rmCode": "string",
    "rmName": "string",
    "mobileNumber": "string",
    "emailId": "string",
    "id": "string"
}]
```

&#x20;You can also pass \`filter\` in query to get all instances matching particular properties.

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfRms?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}

### BM6-Find first matching result <a href="#bm6-find-first-matching-result" id="bm6-find-first-matching-result"></a>

This API endpoint helps you retrieve first data object matching the given properties, pass the filter argument in query, please see example url.

URL : /utilities/masterOfRms/findOne

Method Type : GET

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfRms/findOne?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}
>
> Response JSON

```
{
    "rmCode": "string",
    "rmName": "string",
    "mobileNumber": "string",
    "emailId": "string",
    "id": "string"
}
```

### BM6-Find by id <a href="#bm6-find-by-id" id="bm6-find-by-id"></a>

This API endpoint helps you retrieve data object matching unique object id, just pass the id replacing _{id}_ in the endpoint.

URL : /utilities/masterOfRms/{id}

Method Type : GET

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfRms/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
    "rmCode": "string",
    "rmName": "string",
    "mobileNumber": "string",
    "emailId": "string",
    "id": "string"
}
```

### BM6-Insert data into master <a href="#bm6-insert-data-into-master" id="bm6-insert-data-into-master"></a>

This API endpoint lets you save data object into the master, just hit the API with valid JSON object containing master's data.

URL : /utilities/masterOfRms

Method Type : POST

> Request JSON

```
{
    "rmCode": "string",
    "rmName": "string",
    "mobileNumber": "string",
    "emailId": "string"
}
```

> Response JSON

```
{
    "rmCode": "string",
    "rmName": "string",
    "mobileNumber": "string",
    "emailId": "string",
    "id": "string"
}
```

### BM6-Delete from master <a href="#bm6-delete-from-master" id="bm6-delete-from-master"></a>

This API endpoint helps you delete data object matching unique object id, returns number of documents affected.

URL : /utilities/masterOfRms/{id}

Method Type : DELETE

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfRms/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
    "count": 1
}
```

### BM6-Update data into master <a href="#bm6-update-data-into-master" id="bm6-update-data-into-master"></a>

This API endpoint allows you to update all documents found by where filter with new values specified in body and returns number of documents modified.

URL : /utilities/masterOfRms/update

Method Type : POST

> Example URL with filter : https://indusind-dev.signzy.tech/utilities/masterOfRms/update?where={"property\_one": "value\_one","property\_two": "value\_two"}
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
