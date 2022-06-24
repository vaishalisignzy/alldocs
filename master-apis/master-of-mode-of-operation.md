# Master Of Mode Of Operation



Changes in this master are reflected on the mode of operation dropdown on entity creation screen.

#### FM2-Available HTTP Endpoints <a href="#fm2-available-http-endpoints" id="fm2-available-http-endpoints"></a>

* _Get all data_

**GET** : /utilities/masterOfModeOfOperations

* _Find one_

**GET** : /utilities/masterOfModeOfOperations/findOne

* _Find by id_

**GET** : /utilities/masterOfModeOfOperations/{id}

* _Insert data into master_

**POST** : /utilities/masterOfModeOfOperations

* _Update data into master_

**POST** : /utilities/masterOfModeOfOperations/update

* _Delete data from master_

**DELETE** : /utilities/masterOfModeOfOperations/{id}

#### FM2-Headers <a href="#fm2-headers" id="fm2-headers"></a>

| Property     | Value            |
| ------------ | ---------------- |
| Content-type | application/json |
| Accept       | application/json |

### FM2-Available Properties <a href="#fm2-available-properties" id="fm2-available-properties"></a>

* operationCode
* operationName
* entityName
*   entitytype\


    ![](https://docs.google.com/a/signzy.com/drawings/d/s4qU4QiAUBon-DP8aEizosA/image?w=446\&h=570\&rev=119\&ac=1\&parent=1bj6XdXh9aqjwlWRgAcCYzupCPl8MiI2qebMj-zRTPi4)





### FM2-Get All Data <a href="#fm2-get-all-data" id="fm2-get-all-data"></a>

This API endpoint helps you retrieve all the data objects stored in database with their unique Ids.

URL : /utilities/masterOfModeOfOperations

Method Type : GET

> Response JSON

```
[{
  "operationCode": "string",
  "operationName": "string",
  "entityName": "string",
  "entityType": "string",
  "id": "string"
}]
```

&#x20;You can also pass \`filter\` in query to get all instances matching particular properties.

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfModeOfOperations?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}

### FM2-Find first matching result <a href="#fm2-find-first-matching-result" id="fm2-find-first-matching-result"></a>

This API endpoint helps you retrieve first data object matching the given properties, pass the filter argument in query, please see example url.

URL : /utilities/masterOfModeOfOperations/findOne

Method Type : GET

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfModeOfOperations/findOne?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}
>
> Response JSON

```
{
  "operationCode": "string",
  "operationName": "string",
  "entityName": "string",
  "entityType": "string",
  "id": "string"
}
```

### FM2-Find by id <a href="#fm2-find-by-id" id="fm2-find-by-id"></a>

This API endpoint helps you retrieve data object matching unique object id, just pass the id replacing _{id}_ in the endpoint.

URL : /utilities/masterOfModeOfOperations/{id}

Method Type : GET

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfModeOfOperations/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
  "operationCode": "string",
  "operationName": "string",
  "entityName": "string",
  "entityType": "string",
  "id": "string"
}
```

### FM2-Insert data into master <a href="#fm2-insert-data-into-master" id="fm2-insert-data-into-master"></a>

This API endpoint lets you save data object into the master, just hit the API with valid JSON object containing master's data.

URL : /utilities/masterOfModeOfOperations

Method Type : POST

> Request JSON

```
{
  "operationCode": "string",
  "operationName": "string",
  "entityName": "string",
  "entityType": "string"
}
```

> Response JSON

```
{
  "operationCode": "string",
  "operationName": "string",
  "entityName": "string",
  "entityType": "string",
  "id": "string"
}
```

### FM2-Delete from master <a href="#fm2-delete-from-master" id="fm2-delete-from-master"></a>

This API endpoint helps you delete data object matching unique object id, returns number of documents affected.

URL : /utilities/masterOfModeOfOperations/{id}

Method Type : DELETE

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfModeOfOperations/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
    "count": 1
}
```

### FM2-Update data into master <a href="#fm2-update-data-into-master" id="fm2-update-data-into-master"></a>

This API endpoint allows you to update all documents found by where filter with new values specified in body and returns number of documents modified.

URL : /utilities/masterOfModeOfOperations/update

Method Type : POST

> Example URL with filter : https://indusind-dev.signzy.tech/utilities/masterOfModeOfOperations/update?where={"property\_one": "value\_one","property\_two": "value\_two"}
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
