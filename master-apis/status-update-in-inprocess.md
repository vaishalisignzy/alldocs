# Status Update In Inprocess



This api is used to update status of the leads which have been moved to "inprocess", status will be visible in the "INPROCESS" tab of RM dashboard on the android application.

#### IW1-Available HTTP Endpoints <a href="#iw1-available-http-endpoints" id="iw1-available-http-endpoints"></a>

* _Get all data_

**GET** : /utilities/statusUpdateInInProcess

* _Find one_

**GET** : /utilities/statusUpdateInInProcess/findOne

* _Find by id_

**GET** : /utilities/statusUpdateInInProcess/{id}

* _Create an update_

**POST** : /utilities/statusUpdateInInProcess

* _Update properties_

**POST** : /utilities/statusUpdateInInProcess/update

* _Delete data_

**DELETE** : /utilities/statusUpdateInInProcess/{id}

#### IW1-Headers <a href="#iw1-headers" id="iw1-headers"></a>

| Property     | Value            |
| ------------ | ---------------- |
| Content-type | application/json |
| Accept       | application/json |

### IW1-Available Properties <a href="#iw1-available-properties" id="iw1-available-properties"></a>

* signzyApplicationId
* status
* remarks

### IW1- Possible Values

* status : "DVU verification" , "Exception to RM"

### IW1-Get All Data <a href="#iw1-get-all-data" id="iw1-get-all-data"></a>

This API endpoint helps you retrieve all the data objects stored in database with their unique Ids.

URL : /utilities/statusUpdateInInProcess

Method Type : GET

> Response JSON

```
[{
    "signzyApplicationId": "string",
    "status": "string",
    "remarks": "string",
    "id": "string"
}]
```

&#x20;You can also pass \`filter\` in query to get all instances matching particular properties.

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/statusUpdateInInProcess?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}

### IW1-Find first matching result <a href="#iw1-find-first-matching-result" id="iw1-find-first-matching-result"></a>

This API endpoint helps you retrieve first data object matching the given properties, pass the filter argument in query, please see example url.

URL : /utilities/statusUpdateInInProcess/findOne

Method Type : GET

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/statusUpdateInInProcess/findOne?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}
>
> Response JSON

```
{
    "signzyApplicationId": "string",
    "status": "string",
    "remarks": "string",
    "id": "string"
}
```

### IW1-Find by id <a href="#iw1-find-by-id" id="iw1-find-by-id"></a>

This API endpoint helps you retrieve data object matching unique object id, just pass the id replacing _{id}_ in the endpoint.

URL : /utilities/statusUpdateInInProcess/{id}

Method Type : GET

> Example URL : https://indusind-dev.signzy.tech/utilities/statusUpdateInInProcess/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
    "signzyApplicationId": "string",
    "status": "string",
    "remarks": "string",
    "id": "string"
}
```

### IW1-Create an update <a href="#iw1-create-an-update" id="iw1-create-an-update"></a>

This API endpoint lets you create an update object for a lead, just hit the API with valid JSON object containing update's data.

URL : /utilities/statusUpdateInInProcess

Method Type : POST

> Request JSON

```
{
    "signzyApplicationId": "string",
    "status": "string",
    "remarks": "string"
}
```

> Response JSON

```
{
    "signzyApplicationId": "string",
    "status": "string",
    "remarks": "string",
    "id": "string"
}
```

### IW1-Delete data <a href="#iw1-delete-data" id="iw1-delete-data"></a>

This API endpoint helps you delete data object matching unique object id, returns number of documents affected.

URL : /utilities/statusUpdateInInProcess/{id}

Method Type : DELETE

> Example URL : https://indusind-dev.signzy.tech/utilities/statusUpdateInInProcess/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
    "count": 1
}
```

### IW1-Update properties <a href="#iw1-update-properties" id="iw1-update-properties"></a>

This API endpoint allows you to update all documents found by where filter with new values specified in body and returns number of documents modified.

URL : /utilities/statusUpdateInInProcess/update

Method Type : POST

> Example URL with filter : https://indusind-dev.signzy.tech/utilities/statusUpdateInInProcess/update?where={"property\_one": "value\_one","property\_two": "value\_two"}
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
