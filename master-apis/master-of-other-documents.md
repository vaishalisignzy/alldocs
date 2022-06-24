# Master Of Other Documents



Changes in this master are reflected on the other documents to be uploaded in the flow.

#### FM6-Available HTTP Endpoints <a href="#fm6-available-http-endpoints" id="fm6-available-http-endpoints"></a>

* _Get all data_

**GET** : /utilities/masterOfOtherDocuments

* _Find one_

**GET** : /utilities/masterOfOtherDocuments/findOne

* _Find by id_

**GET** : /utilities/masterOfOtherDocuments/{id}

* _Insert data into master_

**POST** : /utilities/masterOfOtherDocuments

* _Update data into master_

**POST** : /utilities/masterOfOtherDocuments/update

* _Delete data from master_

**DELETE** : /utilities/masterOfOtherDocuments/{id}

#### FM6-Headers <a href="#fm6-headers" id="fm6-headers"></a>

| Property     | Value            |
| ------------ | ---------------- |
| Content-type | application/json |
| Accept       | application/json |

### FM6-Available Properties <a href="#fm6-available-properties" id="fm6-available-properties"></a>

* entityCode
* entityName
* documentName
* documentCode
* mandatory ("Y" or "N")

### FM6- Document Code corresponding to Iworks & RM App <a href="#fm6-available-properties" id="fm6-available-properties"></a>

| IWORKS Field Name/ Front-End | DocumentCode/ Field in Master |
| ---------------------------- | ----------------------------- |
| Business Premises Photo      | BPP                           |
| INDUS\_CONNECT\_ONLINE\_FORM | ICOF                          |
| BENEFICIARY\_OWNER\_FORM     | BOF                           |
| MID                          | MID                           |
| CUSTOMER\_PHOTO              | CP                            |

### FM6-Get All Data <a href="#fm6-get-all-data" id="fm6-get-all-data"></a>

This API endpoint helps you retrieve all the data objects stored in database with their unique Ids.

URL : /utilities/masterOfOtherDocuments

Method Type : GET

> Response JSON

```
[{
  "entityCode": "string",
  "entityName": "string",
  "documentName": "string",
  "documentCode": "string",
  "mandatory": "string",
  "id": "string"
}]
```

&#x20;You can also pass \`filter\` in query to get all instances matching particular properties.

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfOtherDocuments?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}

### FM6-Find first matching result <a href="#fm6-find-first-matching-result" id="fm6-find-first-matching-result"></a>

This API endpoint helps you retrieve first data object matching the given properties, pass the filter argument in query, please see example url.

URL : /utilities/masterOfOtherDocuments/findOne

Method Type : GET

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfOtherDocuments/findOne?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}
>
> Response JSON

```
{
  "entityCode": "string",
  "entityName": "string",
  "documentName": "string",
  "documentCode": "string",
  "mandatory": "string",
  "id": "string"
}
```

### FM6-Find by id <a href="#fm6-find-by-id" id="fm6-find-by-id"></a>

This API endpoint helps you retrieve data object matching unique object id, just pass the id replacing _{id}_ in the endpoint.

URL : /utilities/masterOfOtherDocuments/{id}

Method Type : GET

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfOtherDocuments/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
  "entityCode": "string",
  "entityName": "string",
  "documentName": "string",
  "documentCode": "string",
  "mandatory": "string",
  "id": "string"
}
```

### FM6-Insert data into master <a href="#fm6-insert-data-into-master" id="fm6-insert-data-into-master"></a>

This API endpoint lets you save data object into the master, just hit the API with valid JSON object containing master's data.

URL : /utilities/masterOfOtherDocuments

Method Type : POST

> Request JSON

```
{
  "entityCode": "string",
  "entityName": "string",
  "documentName": "string",
  "documentCode": "string",
  "mandatory": "string"
}
```

> Response JSON

```
{
  "entityCode": "string",
  "entityName": "string",
  "documentName": "string",
  "documentCode": "string",
  "mandatory": "string",
  "id": "string"
}
```

### FM6-Delete from master <a href="#fm6-delete-from-master" id="fm6-delete-from-master"></a>

This API endpoint helps you delete data object matching unique object id, returns number of documents affected.

URL : /utilities/masterOfOtherDocuments/{id}

Method Type : DELETE

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfOtherDocuments/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
    "count": 1
}
```

### FM6-Update data into master <a href="#fm6-update-data-into-master" id="fm6-update-data-into-master"></a>

This API endpoint allows you to update all documents found by where filter with new values specified in body and returns number of documents modified.

URL : /utilities/masterOfOtherDocuments/update

Method Type : POST

> Example URL with filter : https://indusind-dev.signzy.tech/utilities/masterOfOtherDocuments/update?where={"property\_one": "value\_one","property\_two": "value\_two"}
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
