# Master Of Pincode



This master is used to create database for pincodes and related properties which are passed to various apis like finacle, iWorks etc.

#### BM5-Available HTTP Endpoints <a href="#bm5-available-http-endpoints" id="bm5-available-http-endpoints"></a>

* _Get all data_

**GET** : /utilities/masterOfPincodes

* _Find one_

**GET** : /utilities/masterOfPincodes/findOne

* _Find by id_

**GET** : /utilities/masterOfPincodes/{id}

* _Insert data into master_

**POST** : /utilities/masterOfPincodes

* _Update data into master_

**POST** : /utilities/masterOfPincodes/update

* _Delete data from master_

**DELETE** : /utilities/masterOfPincodes/{id}

#### BM5-Headers <a href="#bm5-headers" id="bm5-headers"></a>

| Property     | Value            |
| ------------ | ---------------- |
| Content-type | application/json |
| Accept       | application/json |

### BM5-Available Properties <a href="#bm5-available-properties" id="bm5-available-properties"></a>

* serialNumber
* pincode
* cityCode
* city
* stateCode
* state
* countryCode
* country
* lastModified
* identity

### BM5-Get All Data <a href="#bm5-get-all-data" id="bm5-get-all-data"></a>

This API endpoint helps you retrieve all the data objects stored in database with their unique Ids.

URL : /utilities/masterOfPincodes

Method Type : GET

> Response JSON

```
[{
  "serialNumber": "string",
  "pincode": "string",
  "cityCode": "string",
  "city": "string",
  "stateCode": "string",
  "state": "string",
  "countryCode": "string",
  "country": "string",
  "lastModified": "string",
  "identity": "string",
  "id": "string"
}]
```

&#x20;You can also pass \`filter\` in query to get all instances matching particular properties.

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfPincodes?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}

### BM5-Find first matching result <a href="#bm5-find-first-matching-result" id="bm5-find-first-matching-result"></a>

This API endpoint helps you retrieve first data object matching the given properties, pass the filter argument in query, please see example url.

URL : /utilities/masterOfPincodes/findOne

Method Type : GET

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfPincodes/findOne?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}
>
> Response JSON

```
{
  "serialNumber": "string",
  "pincode": "string",
  "cityCode": "string",
  "city": "string",
  "stateCode": "string",
  "state": "string",
  "countryCode": "string",
  "country": "string",
  "lastModified": "string",
  "identity": "string",
  "id": "string"
}
```

### BM5-Find by id <a href="#bm5-find-by-id" id="bm5-find-by-id"></a>

This API endpoint helps you retrieve data object matching unique object id, just pass the id replacing _{id}_ in the endpoint.

URL : /utilities/masterOfPincodes/{id}

Method Type : GET

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfPincodes/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
  "serialNumber": "string",
  "pincode": "string",
  "cityCode": "string",
  "city": "string",
  "stateCode": "string",
  "state": "string",
  "countryCode": "string",
  "country": "string",
  "lastModified": "string",
  "identity": "string",
  "id": "string"
}
```

### BM5-Insert data into master <a href="#bm5-insert-data-into-master" id="bm5-insert-data-into-master"></a>

This API endpoint lets you save data object into the master, just hit the API with valid JSON object containing master's data.

URL : /utilities/masterOfPincodes

Method Type : POST

> Request JSON

```
{
  "serialNumber": "string",
  "pincode": "string",
  "cityCode": "string",
  "city": "string",
  "stateCode": "string",
  "state": "string",
  "countryCode": "string",
  "country": "string",
  "lastModified": "string",
  "identity": "string"
}
```

> Response JSON

```
{
  "serialNumber": "string",
  "pincode": "string",
  "cityCode": "string",
  "city": "string",
  "stateCode": "string",
  "state": "string",
  "countryCode": "string",
  "country": "string",
  "lastModified": "string",
  "identity": "string",
  "id": "string"
}
```

### BM5-Delete from master <a href="#bm5-delete-from-master" id="bm5-delete-from-master"></a>

This API endpoint helps you delete data object matching unique object id, returns number of documents affected.

URL : /utilities/masterOfPincodes/{id}

Method Type : DELETE

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfPincodes/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
    "count": 1
}
```

### BM5-Update data into master <a href="#bm5-update-data-into-master" id="bm5-update-data-into-master"></a>

This API endpoint allows you to update all documents found by where filter with new values specified in body and returns number of documents modified.

URL : /utilities/masterOfPincodes/update

Method Type : POST

> Example URL with filter : https://indusind-dev.signzy.tech/utilities/masterOfPincodes/update?where={"property\_one": "value\_one","property\_two": "value\_two"}
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
