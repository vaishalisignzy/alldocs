# Master Of Declarations



Changes in this master are reflected on the declaration screen in the flow.

#### FM8-Available HTTP Endpoints <a href="#fm8-available-http-endpoints" id="fm8-available-http-endpoints"></a>

* _Get all data_

**GET** : /utilities/masterOfDeclarations

* _Find one_

**GET** : /utilities/masterOfDeclarations/findOne

* _Find by id_

**GET** : /utilities/masterOfDeclarations/{id}

* _Insert data into master_

**POST** : /utilities/masterOfDeclarations

* _Update data into master_

**POST** : /utilities/masterOfDeclarations/update

* _Delete data from master_

**DELETE** : /utilities/masterOfDeclarations/{id}

#### FM8-Headers <a href="#fm8-headers" id="fm8-headers"></a>

| Property     | Value            |
| ------------ | ---------------- |
| Content-type | application/json |
| Accept       | application/json |

### FM8-Available Properties <a href="#fm8-available-properties" id="fm8-available-properties"></a>

* declarationCode
* declarationName
* entityCode
* declarationMessage

### FM8-Get All Data <a href="#fm8-get-all-data" id="fm8-get-all-data"></a>

This API endpoint helps you retrieve all the data objects stored in database with their unique Ids.

URL : /utilities/masterOfDeclarations

Method Type : GET

> Response JSON

```
[{
  "declarationCode": "string",
  "declarationName": "string",
  "entityCode": "string",
  "declarationMessage": "string",
  "id": "string"
}]
```

&#x20;You can also pass \`filter\` in query to get all instances matching particular properties.

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfDeclarations?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}

### FM8-Find first matching result <a href="#fm8-find-first-matching-result" id="fm8-find-first-matching-result"></a>

This API endpoint helps you retrieve first data object matching the given properties, pass the filter argument in query, please see example url.

URL : /utilities/masterOfDeclarations/findOne

Method Type : GET

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfDeclarations/findOne?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}
>
> Response JSON

```
{
  "declarationCode": "string",
  "declarationName": "string",
  "entityCode": "string",
  "declarationMessage": "string",
  "id": "string"
}
```

### FM8-Find by id <a href="#fm8-find-by-id" id="fm8-find-by-id"></a>

This API endpoint helps you retrieve data object matching unique object id, just pass the id replacing _{id}_ in the endpoint.

URL : /utilities/masterOfDeclarations/{id}

Method Type : GET

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfDeclarations/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
  "declarationCode": "string",
  "declarationName": "string",
  "entityCode": "string",
  "declarationMessage": "string",
  "id": "string"
}
```

### FM8-Insert data into master <a href="#fm8-insert-data-into-master" id="fm8-insert-data-into-master"></a>

This API endpoint lets you save data object into the master, just hit the API with valid JSON object containing master's data.

URL : /utilities/masterOfDeclarations

Method Type : POST

> Request JSON

```
{
  "declarationCode": "string",
  "declarationName": "string",
  "entityCode": "string",
  "declarationMessage": "string"
}
```

> Response JSON

```
{
  "declarationCode": "string",
  "declarationName": "string",
  "entityCode": "string",
  "declarationMessage": "string",
  "id": "string"
}
```

### FM8-Delete from master <a href="#fm8-delete-from-master" id="fm8-delete-from-master"></a>

This API endpoint helps you delete data object matching unique object id, returns number of documents affected.

URL : /utilities/masterOfDeclarations/{id}

Method Type : DELETE

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfDeclarations/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
    "count": 1
}
```

### FM8-Update data into master <a href="#fm8-update-data-into-master" id="fm8-update-data-into-master"></a>

This API endpoint allows you to update all documents found by where filter with new values specified in body and returns number of documents modified.

URL : /utilities/masterOfDeclarations/update

Method Type : POST

> Example URL with filter : https://indusind-dev.signzy.tech/utilities/masterOfDeclarations/update?where={"property\_one": "value\_one","property\_two": "value\_two"}
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
