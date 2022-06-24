# Move To Account Opened

This api is used to update status of the leads to "Account Opened" and move leads from "INPROCESS" tab to Accounts Opened page on the android application. This API is also used to update CIF number and Account Number of the entity.

#### IW2-Available HTTP Endpoints <a href="#iw2-available-http-endpoints" id="iw2-available-http-endpoints"></a>

* _Get all data_

**GET** : /utilities/moveToAccountOpened

* _Find one_

**GET** : /utilities/moveToAccountOpened/findOne

* _Find by id_

**GET** : /utilities/moveToAccountOpened/{id}

* _Create an update_

**POST** : /utilities/moveToAccountOpened

* _Update properties_

**POST** : /utilities/moveToAccountOpened/update

* _Delete data_

**DELETE** : /utilities/moveToAccountOpened/{id}

#### IW2-Headers <a href="#iw2-headers" id="iw2-headers"></a>

| Property     | Value            |
| ------------ | ---------------- |
| Content-type | application/json |
| Accept       | application/json |

### IW2-Available Properties <a href="#iw2-available-properties" id="iw2-available-properties"></a>

* signzyApplicationId
* cif
* accountNumber
* status

### IW2- Possible Values

* status : "Account opened"

### IW2-Get All Data <a href="#iw2-get-all-data" id="iw2-get-all-data"></a>

This API endpoint helps you retrieve all the data objects stored in database with their unique Ids.

URL : /utilities/moveToAccountOpened

Method Type : GET

> Response JSON

```
[{
    "signzyApplicationId": "string",
    "cif": "string",
    "accountNumber": "string",
    "status": "string",
    "id": "string"
}]
```

&#x20;You can also pass \`filter\` in query to get all instances matching particular properties.

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/moveToAccountOpened?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}

### IW2-Find first matching result <a href="#iw2-find-first-matching-result" id="iw2-find-first-matching-result"></a>

This API endpoint helps you retrieve first data object matching the given properties, pass the filter argument in query, please see example url.

URL : /utilities/moveToAccountOpened/findOne

Method Type : GET

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/moveToAccountOpened/findOne?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}
>
> Response JSON

```
{
    "signzyApplicationId": "string",
    "cif": "string",
    "accountNumber": "string",
    "status": "string",
    "id": "string"
}
```

### IW2-Find by id <a href="#iw2-find-by-id" id="iw2-find-by-id"></a>

This API endpoint helps you retrieve data object matching unique object id, just pass the id replacing _{id}_ in the endpoint.

URL : /utilities/moveToAccountOpened/{id}

Method Type : GET

> Example URL : https://indusind-dev.signzy.tech/utilities/moveToAccountOpened/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
    "signzyApplicationId": "string",
    "cif": "string",
    "accountNumber": "string",
    "status": "string",
    "id": "string"
}
```

### IW2-Create an update <a href="#iw2-create-an-update" id="iw2-create-an-update"></a>

This API endpoint lets you create an update object for a lead, just hit the API with valid JSON object containing update's data.

URL : /utilities/moveToAccountOpened

Method Type : POST

> Request JSON

```
{
    "signzyApplicationId": "string",
    "cif": "string",
    "accountNumber": "string",
    "status": "string"
}
```

> Response JSON

```
{
    "signzyApplicationId": "string",
    "cif": "string",
    "accountNumber": "string",
    "status": "string",
    "id": "string"
}
```

### IW2-Delete data <a href="#iw2-delete-data" id="iw2-delete-data"></a>

This API endpoint helps you delete data object matching unique object id, returns number of documents affected.

URL : /utilities/moveToAccountOpened/{id}

Method Type : DELETE

> Example URL : https://indusind-dev.signzy.tech/utilities/moveToAccountOpened/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
    "count": 1
}
```

### IW2-Update properties <a href="#iw2-update-properties" id="iw2-update-properties"></a>

This API endpoint allows you to update all documents found by where filter with new values specified in body and returns number of documents modified.

URL : /utilities/moveToAccountOpened/update

Method Type : POST

> Example URL with filter : https://indusind-dev.signzy.tech/utilities/moveToAccountOpened/update?where={"property\_one": "value\_one","property\_two": "value\_two"}
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
