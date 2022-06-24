# Master Of Field Verification Agency



This master contain details of field verification agencies which will be sent an email regarding the customer which they have to verify, agency will be assigned based on the bank branch selected by the customer on the entity creation screen.

#### BM2-Available HTTP Endpoints <a href="#bm2-available-http-endpoints" id="bm2-available-http-endpoints"></a>

* _Get all data_

**GET** : /utilities/masterOfFvs

* _Find one_

**GET** : /utilities/masterOfFvs/findOne

* _Find by id_

**GET** : /utilities/masterOfFvs/{id}

* _Insert data into master_

**POST** : /utilities/masterOfFvs

* _Update data into master_

**POST** : /utilities/masterOfFvs/update

* _Delete data from master_

**DELETE** : /utilities/masterOfFvs/{id}

#### BM2-Headers <a href="#bm2-headers" id="bm2-headers"></a>

| Property     | Value            |
| ------------ | ---------------- |
| Content-type | application/json |
| Accept       | application/json |

### BM2-Available Properties <a href="#bm2-available-properties" id="bm2-available-properties"></a>

* agencyCode
* agencyName
* contactPerson
* mobileNumber
* emailId
* fvServicingBranch

### BM2- Description

| Field Name        | Description                                     |
| ----------------- | ----------------------------------------------- |
| fvServicingBranch | Branch Selected by RM on Entity Creation Screen |

### BM2-Get All Data <a href="#bm2-get-all-data" id="bm2-get-all-data"></a>

This API endpoint helps you retrieve all the data objects stored in database with their unique Ids.

URL : /utilities/masterOfFvs

Method Type : GET

> Response JSON

```
[{
  "agencyCode": "string",
  "agencyName": "string",
  "contactPerson": "string",
  "mobileNumber": "string",
  "emailId": "string",
  "fvServicingBranch": "string",
  "id": "string"
}]
```

&#x20;You can also pass \`filter\` in query to get all instances matching particular properties.

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfFvs?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}

### BM2-Find first matching result <a href="#bm2-find-first-matching-result" id="bm2-find-first-matching-result"></a>

This API endpoint helps you retrieve first data object matching the given properties, pass the filter argument in query, please see example url.

URL : /utilities/masterOfFvs/findOne

Method Type : GET

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfFvs/findOne?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}
>
> Response JSON

```
{
  "agencyCode": "string",
  "agencyName": "string",
  "contactPerson": "string",
  "mobileNumber": "string",
  "emailId": "string",
  "fvServicingBranch": "string",
  "id": "string"
}
```

### BM2-Find by id <a href="#bm2-find-by-id" id="bm2-find-by-id"></a>

This API endpoint helps you retrieve data object matching unique object id, just pass the id replacing _{id}_ in the endpoint.

URL : /utilities/masterOfFvs/{id}

Method Type : GET

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfFvs/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
  "agencyCode": "string",
  "agencyName": "string",
  "contactPerson": "string",
  "mobileNumber": "string",
  "emailId": "string",
  "fvServicingBranch": "string",
  "id": "string"
}
```

### BM2-Insert data into master <a href="#bm2-insert-data-into-master" id="bm2-insert-data-into-master"></a>

This API endpoint lets you save data object into the master, just hit the API with valid JSON object containing master's data.

URL : /utilities/masterOfFvs

Method Type : POST

> Request JSON

```
{
  "agencyCode": "string",
  "agencyName": "string",
  "contactPerson": "string",
  "mobileNumber": "string",
  "emailId": "string",
  "fvServicingBranch": "string",
}
```

> Response JSON

```
{
  "agencyCode": "string",
  "agencyName": "string",
  "contactPerson": "string",
  "mobileNumber": "string",
  "emailId": "string",
  "fvServicingBranch": "string",
  "id": "string"
}
```

### BM2-Delete from master <a href="#bm2-delete-from-master" id="bm2-delete-from-master"></a>

This API endpoint helps you delete data object matching unique object id, returns number of documents affected.

URL : /utilities/masterOfFvs/{id}

Method Type : DELETE

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfFvs/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
    "count": 1
}
```

### BM2-Update data into master <a href="#bm2-update-data-into-master" id="bm2-update-data-into-master"></a>

This API endpoint allows you to update all documents found by where filter with new values specified in body and returns number of documents modified.

URL : /utilities/masterOfFvs/update

Method Type : POST

> Example URL with filter : https://indusind-dev.signzy.tech/utilities/masterOfFvs/update?where={"property\_one": "value\_one","property\_two": "value\_two"}
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
