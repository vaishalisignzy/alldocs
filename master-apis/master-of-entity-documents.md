# Master Of Entity Documents



Changes in this master are reflected on the POA others dropdown in proprietor entity and POA communication for all entities.

#### FM3-Available HTTP Endpoints <a href="#fm3-available-http-endpoints" id="fm3-available-http-endpoints"></a>

* _Get all data_

**GET** : /utilities/masterOfEntityDocuments

* _Find one_

**GET** : /utilities/masterOfEntityDocuments/findOne

* _Find by id_

**GET** : /utilities/masterOfEntityDocuments/{id}

* _Insert data into master_

**POST** : /utilities/masterOfEntityDocuments

* _Update data into master_

**POST** : /utilities/masterOfEntityDocuments/update

* _Delete data from master_

**DELETE** : /utilities/masterOfEntityDocuments/{id}

#### FM3-Headers <a href="#fm3-headers" id="fm3-headers"></a>

| Property     | Value            |
| ------------ | ---------------- |
| Content-type | application/json |
| Accept       | application/json |

### FM3-Available Properties <a href="#fm3-available-properties" id="fm3-available-properties"></a>

* entityCode
* entityType
* proofOfExistence2
*   poaCommunication\
    \


    ![](https://docs.google.com/a/signzy.com/drawings/d/sQl3WMnNpKcY\_Phf0C-8oaw/image?w=534\&h=570\&rev=11\&ac=1\&parent=1bj6XdXh9aqjwlWRgAcCYzupCPl8MiI2qebMj-zRTPi4)

### FM3-Get All Data <a href="#fm3-get-all-data" id="fm3-get-all-data"></a>

This API endpoint helps you retrieve all the data objects stored in database with their unique Ids.

URL : /utilities/masterOfEntityDocuments

Method Type : GET

> Response JSON

```
[{
  "entityCode": "string",
  "entityType": "string",
  "proofOfExistence2": "string",
  "poaCommunication": "string",
  "id": "string"
}]
```

&#x20;You can also pass \`filter\` in query to get all instances matching particular properties.

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfEntityDocuments?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}

### FM3-Find first matching result <a href="#fm3-find-first-matching-result" id="fm3-find-first-matching-result"></a>

This API endpoint helps you retrieve first data object matching the given properties, pass the filter argument in query, please see example url.

URL : /utilities/masterOfEntityDocuments/findOne

Method Type : GET

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfEntityDocuments/findOne?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}
>
> Response JSON

```
{
  "entityCode": "string",
  "entityType": "string",
  "proofOfExistence2": "string",
  "poaCommunication": "string",
  "id": "string"
}
```

### FM3-Find by id <a href="#fm3-find-by-id" id="fm3-find-by-id"></a>

This API endpoint helps you retrieve data object matching unique object id, just pass the id replacing _{id}_ in the endpoint.

URL : /utilities/masterOfEntityDocuments/{id}

Method Type : GET

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfEntityDocuments/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
  "entityCode": "string",
  "entityType": "string",
  "proofOfExistence2": "string",
  "poaCommunication": "string",
  "id": "string"
}
```

### FM3-Insert data into master <a href="#fm3-insert-data-into-master" id="fm3-insert-data-into-master"></a>

This API endpoint lets you save data object into the master, just hit the API with valid JSON object containing master's data.

URL : /utilities/masterOfEntityDocuments

Method Type : POST

> Request JSON

```
{
  "entityCode": "string",
  "entityType": "string",
  "proofOfExistence2": "string",
  "poaCommunication": "string"
}
```

> Response JSON

```
{
  "entityCode": "string",
  "entityType": "string",
  "proofOfExistence2": "string",
  "poaCommunication": "string",
  "id": "string"
}
```

### FM3-Delete from master <a href="#fm3-delete-from-master" id="fm3-delete-from-master"></a>

This API endpoint helps you delete data object matching unique object id, returns number of documents affected.

URL : /utilities/masterOfEntityDocuments/{id}

Method Type : DELETE

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfEntityDocuments/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
    "count": 1
}
```

### FM3-Update data into master <a href="#fm3-update-data-into-master" id="fm3-update-data-into-master"></a>

This API endpoint allows you to update all documents found by where filter with new values specified in body and returns number of documents modified.

URL : /utilities/masterOfEntityDocuments/update

Method Type : POST

> Example URL with filter : https://indusind-dev.signzy.tech/utilities/masterOfEntityDocuments/update?where={"property\_one": "value\_one","property\_two": "value\_two"}
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

