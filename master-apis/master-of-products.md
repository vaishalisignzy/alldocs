# Master Of Products



Changes in this master are reflected on the recommended and other products screen.

#### FM9-Available HTTP Endpoints <a href="#fm9-available-http-endpoints" id="fm9-available-http-endpoints"></a>

* _Get all data_

**GET** : /utilities/masterOfProducts

* _Find one_

**GET** : /utilities/masterOfProducts/findOne

* _Find by id_

**GET** : /utilities/masterOfProducts/{id}

* _Insert data into master_

**POST** : /utilities/masterOfProducts

* _Update data into master_

**POST** : /utilities/masterOfProducts/update

* _Delete data from master_

**DELETE** : /utilities/masterOfProducts/{id}

#### FM9-Headers <a href="#fm9-headers" id="fm9-headers"></a>

| Property     | Value            |
| ------------ | ---------------- |
| Content-type | application/json |
| Accept       | application/json |

### FM9-Available Properties <a href="#fm9-available-properties" id="fm9-available-properties"></a>

* productCode
* productDescription
* productImage
* productUrl
* salientFeature1
* salientFeature2
* salientFeature3
* salientFeature4
* salientFeature5
* salientFeature6
* salientFeature7
* salientFeature8
* salientFeature9
* salientFeature10

### FM9-Get All Data <a href="#fm9-get-all-data" id="fm9-get-all-data"></a>

This API endpoint helps you retrieve all the data objects stored in database with their unique Ids.

URL : /utilities/masterOfProducts

Method Type : GET

> Response JSON

```
[{
  "productCode": "string",
  "productDescription": "string",
  "productImage": "string",
  "productUrl": "string",
  "salientFeature1": "string",
  "salientFeature2": "string",
  "salientFeature3": "string",
  "salientFeature4": "string",
  "salientFeature5": "string",
  "salientFeature6": "string",
  "salientFeature7": "string",
  "salientFeature8": "string",
  "salientFeature9": "string",
  "salientFeature10": "string",
  "id": "string"
}]
```

&#x20;You can also pass \`filter\` in query to get all instances matching particular properties.

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfProducts?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}

### FM9-Find first matching result <a href="#fm9-find-first-matching-result" id="fm9-find-first-matching-result"></a>

This API endpoint helps you retrieve first data object matching the given properties, pass the filter argument in query, please see example url.

URL : /utilities/masterOfProducts/findOne

Method Type : GET

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfProducts/findOne?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}
>
> Response JSON

```
{
  "productCode": "string",
  "productDescription": "string",
  "productImage": "string",
  "productUrl": "string",
  "salientFeature1": "string",
  "salientFeature2": "string",
  "salientFeature3": "string",
  "salientFeature4": "string",
  "salientFeature5": "string",
  "salientFeature6": "string",
  "salientFeature7": "string",
  "salientFeature8": "string",
  "salientFeature9": "string",
  "salientFeature10": "string",
  "id": "string"
}
```

### FM9-Find by id <a href="#fm9-find-by-id" id="fm9-find-by-id"></a>

This API endpoint helps you retrieve data object matching unique object id, just pass the id replacing _{id}_ in the endpoint.

URL : /utilities/masterOfProducts/{id}

Method Type : GET

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfProducts/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
  "productCode": "string",
  "productDescription": "string",
  "productImage": "string",
  "productUrl": "string",
  "salientFeature1": "string",
  "salientFeature2": "string",
  "salientFeature3": "string",
  "salientFeature4": "string",
  "salientFeature5": "string",
  "salientFeature6": "string",
  "salientFeature7": "string",
  "salientFeature8": "string",
  "salientFeature9": "string",
  "salientFeature10": "string",
  "id": "string"
}
```

### FM9-Insert data into master <a href="#fm9-insert-data-into-master" id="fm9-insert-data-into-master"></a>

This API endpoint lets you save data object into the master, just hit the API with valid JSON object containing master's data.

URL : /utilities/masterOfProducts

Method Type : POST

> Request JSON

```
{
  "productCode": "string",
  "productDescription": "string",
  "productImage": "string",
  "productUrl": "string",
  "salientFeature1": "string",
  "salientFeature2": "string",
  "salientFeature3": "string",
  "salientFeature4": "string",
  "salientFeature5": "string",
  "salientFeature6": "string",
  "salientFeature7": "string",
  "salientFeature8": "string",
  "salientFeature9": "string",
  "salientFeature10": "string"
}
```

> Response JSON

```
{
  "productCode": "string",
  "productDescription": "string",
  "productImage": "string",
  "productUrl": "string",
  "salientFeature1": "string",
  "salientFeature2": "string",
  "salientFeature3": "string",
  "salientFeature4": "string",
  "salientFeature5": "string",
  "salientFeature6": "string",
  "salientFeature7": "string",
  "salientFeature8": "string",
  "salientFeature9": "string",
  "salientFeature10": "string",
  "id": "string"
}
```

### FM9-Delete from master <a href="#fm9-delete-from-master" id="fm9-delete-from-master"></a>

This API endpoint helps you delete data object matching unique object id, returns number of documents affected.

URL : /utilities/masterOfProducts/{id}

Method Type : DELETE

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfProducts/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
    "count": 1
}
```

### FM9-Update data into master <a href="#fm9-update-data-into-master" id="fm9-update-data-into-master"></a>

This API endpoint allows you to update all documents found by where filter with new values specified in body and returns number of documents modified.

URL : /utilities/masterOfProducts/update

Method Type : POST

> Example URL with filter : https://indusind-dev.signzy.tech/utilities/masterOfProducts/update?where={"property\_one": "value\_one","property\_two": "value\_two"}
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
