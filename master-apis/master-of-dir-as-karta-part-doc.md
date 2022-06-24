# Master Of Dir-AS-Karta-Part-Doc



Changes in this master are reflected on POA communication dropdown in the flow.

#### FM4-Available HTTP Endpoints <a href="#fm4-available-http-endpoints" id="fm4-available-http-endpoints"></a>

* _Get all data_

**GET** : /utilities/masterOfDakpds

* _Find one_

**GET** : /utilities/masterOfDakpds/findOne

* _Find by id_

**GET** : /utilities/masterOfDakpds/{id}

* _Insert data into master_

**POST** : /utilities/masterOfDakpds

* _Update data into master_

**POST** : /utilities/masterOfDakpds/update

* _Delete data from master_

**DELETE** : /utilities/masterOfDakpds/{id}

#### FM4-Headers <a href="#fm4-headers" id="fm4-headers"></a>

| Property     | Value            |
| ------------ | ---------------- |
| Content-type | application/json |
| Accept       | application/json |

### FM4-Available Properties <a href="#fm4-available-properties" id="fm4-available-properties"></a>

* communicationAddressDocument

### FM4-Get All Data <a href="#fm4-get-all-data" id="fm4-get-all-data"></a>

This API endpoint helps you retrieve all the data objects stored in database with their unique Ids.

URL : /utilities/masterOfDakpds

Method Type : GET

> Response JSON

```
[{
  "communicationAddressDocument": "string",
  "id": "string"
}]
```

&#x20;You can also pass \`filter\` in query to get all instances matching particular properties.

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfDakpds?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}

### FM4-Find first matching result <a href="#fm4-find-first-matching-result" id="fm4-find-first-matching-result"></a>

This API endpoint helps you retrieve first data object matching the given properties, pass the filter argument in query, please see example url.

URL : /utilities/masterOfDakpds/findOne

Method Type : GET

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfDakpds/findOne?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}
>
> Response JSON

```
{
  "communicationAddressDocument": "string",
  "id": "string"
}
```

### FM4-Find by id <a href="#fm4-find-by-id" id="fm4-find-by-id"></a>

This API endpoint helps you retrieve data object matching unique object id, just pass the id replacing _{id}_ in the endpoint.

URL : /utilities/masterOfDakpds/{id}

Method Type : GET

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfDakpds/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
  "communicationAddressDocument": "string",
  "id": "string"
}
```

### FM4-Insert data into master <a href="#fm4-insert-data-into-master" id="fm4-insert-data-into-master"></a>

This API endpoint lets you save data object into the master, just hit the API with valid JSON object containing master's data.

URL : /utilities/masterOfDakpds

Method Type : POST

> Request JSON

```
{
  "communicationAddressDocument": "string"
}
```

> Response JSON

```
{
  "communicationAddressDocument": "string",
  "id": "string"
}
```

### FM4-Delete from master <a href="#fm4-delete-from-master" id="fm4-delete-from-master"></a>

This API endpoint helps you delete data object matching unique object id, returns number of documents affected.

URL : /utilities/masterOfDakpds/{id}

Method Type : DELETE

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfDakpds/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
    "count": 1
}
```

### FM4-Update data into master <a href="#fm4-update-data-into-master" id="fm4-update-data-into-master"></a>

This API endpoint allows you to update all documents found by where filter with new values specified in body and returns number of documents modified.

URL : /utilities/masterOfDakpds/update

Method Type : POST

> Example URL with filter : https://indusind-dev.signzy.tech/utilities/masterOfDakpds/update?where={"property\_one": "value\_one","property\_two": "value\_two"}
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
