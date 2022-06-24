# Master Of RM Declarations



Changes in this master are reflected on the RM declaration screen in the flow.

#### FM10-Available HTTP Endpoints <a href="#fm10-available-http-endpoints" id="fm10-available-http-endpoints"></a>

* _Get all data_

**GET** : /utilities/masterOfRmDeclarations

* _Find one_

**GET** : /utilities/masterOfRmDeclarations/findOne

* _Find by id_

**GET** : /utilities/masterOfRmDeclarations/{id}

* _Insert data into master_

**POST** : /utilities/masterOfRmDeclarations

* _Update data into master_

**POST** : /utilities/masterOfRmDeclarations/update

* _Delete data from master_

**DELETE** : /utilities/masterOfRmDeclarations/{id}

#### FM10-Headers <a href="#fm10-headers" id="fm10-headers"></a>

| Property     | Value            |
| ------------ | ---------------- |
| Content-type | application/json |
| Accept       | application/json |

### FM10-Available Properties <a href="#fm10-available-properties" id="fm10-available-properties"></a>

* entityCode
* declarationCode
* declarationText
* declarationName

### FM10-Get All Data <a href="#fm10-get-all-data" id="fm10-get-all-data"></a>

This API endpoint helps you retrieve all the data objects stored in database with their unique Ids.

URL : /utilities/masterOfRmDeclarations

Method Type : GET

> Response JSON

```
[{
  "entityCode": "string",
  "declarationCode": "string",
  "declarationText": "string",
  "declarationName": "string",
  "id": "string"
}]
```

&#x20;You can also pass \`filter\` in query to get all instances matching particular properties.

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfRmDeclarations?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}

### FM10-Find first matching result <a href="#fm10-find-first-matching-result" id="fm10-find-first-matching-result"></a>

This API endpoint helps you retrieve first data object matching the given properties, pass the filter argument in query, please see example url.

URL : /utilities/masterOfRmDeclarations/findOne

Method Type : GET

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfRmDeclarations/findOne?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}
>
> Response JSON

```
{
  "entityCode": "string",
  "declarationCode": "string",
  "declarationText": "string",
  "declarationName": "string",
  "id": "string"
}
```

### FM10-Find by id <a href="#fm10-find-by-id" id="fm10-find-by-id"></a>

This API endpoint helps you retrieve data object matching unique object id, just pass the id replacing _{id}_ in the endpoint.

URL : /utilities/masterOfRmDeclarations/{id}

Method Type : GET

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfRmDeclarations/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
  "entityCode": "string",
  "declarationCode": "string",
  "declarationText": "string",
  "declarationName": "string",
  "id": "string"
}
```

### FM10-Insert data into master <a href="#fm10-insert-data-into-master" id="fm10-insert-data-into-master"></a>

This API endpoint lets you save data object into the master, just hit the API with valid JSON object containing master's data.

URL : /utilities/masterOfRmDeclarations

Method Type : POST

> Request JSON

```
{
  "entityCode": "string",
  "declarationCode": "string",
  "declarationText": "string",
  "declarationName": "string"
}
```

> Response JSON

```
{
  "entityCode": "string",
  "declarationCode": "string",
  "declarationText": "string",
  "declarationName": "string",
  "id": "string"
}
```

### FM10-Delete from master <a href="#fm10-delete-from-master" id="fm10-delete-from-master"></a>

This API endpoint helps you delete data object matching unique object id, returns number of documents affected.

URL : /utilities/masterOfRmDeclarations/{id}

Method Type : DELETE

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfRmDeclarations/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
    "count": 1
}
```

### FM10-Update data into master <a href="#fm10-update-data-into-master" id="fm10-update-data-into-master"></a>

This API endpoint allows you to update all documents found by where filter with new values specified in body and returns number of documents modified.

URL : /utilities/masterOfRmDeclarations/update

Method Type : POST

> Example URL with filter : https://indusind-dev.signzy.tech/utilities/masterOfRmDeclarations/update?where={"property\_one": "value\_one","property\_two": "value\_two"}
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
