# Master Of Sub Segment



Changes in this master are reflected on the sub-segment drop down on create entity screen.

#### FM11-Available HTTP Endpoints <a href="#fm11-available-http-endpoints" id="fm11-available-http-endpoints"></a>

* _Get all data_

**GET** : /utilities/masterOfSubSegments

* _Find one_

**GET** : /utilities/masterOfSubSegments/findOne

* _Find by id_

**GET** : /utilities/masterOfSubSegments/{id}

* _Insert data into master_

**POST** : /utilities/masterOfSubSegments

* _Update data into master_

**POST** : /utilities/masterOfSubSegments/update

* _Delete data from master_

**DELETE** : /utilities/masterOfSubSegments/{id}

#### FM11-Headers <a href="#fm11-headers" id="fm11-headers"></a>

| Property     | Value            |
| ------------ | ---------------- |
| Content-type | application/json |
| Accept       | application/json |

### FM11-Available Properties <a href="#fm11-available-properties" id="fm11-available-properties"></a>

* entityCode
* subSegmentCode
* subSegmentText
* debitCard
* netBanking
* bankScreen

### FM11-Get All Data <a href="#fm11-get-all-data" id="fm11-get-all-data"></a>

This API endpoint helps you retrieve all the data objects stored in database with their unique Ids.

URL : /utilities/masterOfSubSegments

Method Type : GET

> Response JSON

```
[{
    "entityCode": "string",
    "subSegmentCode": "string",
    "subSegmentText": "string",
    "debitCard": "string",
    "netBanking": "string",
    "bankScreen": "string",
    "id": "string"
}]
```

&#x20;You can also pass \`filter\` in query to get all instances matching particular properties.

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfSubSegments?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}

### FM11-Find first matching result <a href="#fm11-find-first-matching-result" id="fm11-find-first-matching-result"></a>

This API endpoint helps you retrieve first data object matching the given properties, pass the filter argument in query, please see example url.

URL : /utilities/masterOfSubSegments/findOne

Method Type : GET

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfSubSegments/findOne?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}
>
> Response JSON

```
{
    "entityCode": "string",
    "subSegmentCode": "string",
    "subSegmentText": "string",
    "debitCard": "string",
    "netBanking": "string",
    "bankScreen": "string",
    "id": "string"
}
```

### FM11-Find by id <a href="#fm11-find-by-id" id="fm11-find-by-id"></a>

This API endpoint helps you retrieve data object matching unique object id, just pass the id replacing _{id}_ in the endpoint.

URL : /utilities/masterOfSubSegments/{id}

Method Type : GET

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfSubSegments/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
    "entityCode": "string",
    "subSegmentCode": "string",
    "subSegmentText": "string",
    "debitCard": "string",
    "netBanking": "string",
    "bankScreen": "string",
    "id": "string"
}
```

### FM11-Insert data into master <a href="#fm11-insert-data-into-master" id="fm11-insert-data-into-master"></a>

This API endpoint lets you save data object into the master, just hit the API with valid JSON object containing master's data.

URL : /utilities/masterOfSubSegments

Method Type : POST

> Request JSON

```
{
    "entityCode": "string",
    "subSegmentCode": "string",
    "subSegmentText": "string",
    "debitCard": "string",
    "netBanking": "string",
    "bankScreen": "string",
}
```

> Response JSON

```
{
    "entityCode": "string",
    "subSegmentCode": "string",
    "subSegmentText": "string",
    "debitCard": "string",
    "netBanking": "string",
    "bankScreen": "string",
    "id": "string"
}
```

### FM11-Delete from master <a href="#fm11-delete-from-master" id="fm11-delete-from-master"></a>

This API endpoint helps you delete data object matching unique object id, returns number of documents affected.

URL : /utilities/masterOfSubSegments/{id}

Method Type : DELETE

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfSubSegments/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
    "count": 1
}
```

### FM11-Update data into master <a href="#fm11-update-data-into-master" id="fm11-update-data-into-master"></a>

This API endpoint allows you to update all documents found by where filter with new values specified in body and returns number of documents modified.

URL : /utilities/masterOfSubSegments/update

Method Type : POST

> Example URL with filter : https://indusind-dev.signzy.tech/utilities/masterOfSubSegments/update?where={"property\_one": "value\_one","property\_two": "value\_two"}
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
