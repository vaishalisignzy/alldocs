# Master Of Cards



Changes in this master are reflected on cards selection screen in the flow.

#### FM5-Available HTTP Endpoints <a href="#fm5-available-http-endpoints" id="fm5-available-http-endpoints"></a>

* _Get all data_

**GET** : /utilities/masterOfCards

* _Find one_

**GET** : /utilities/masterOfCards/findOne

* _Find by id_

**GET** : /utilities/masterOfCards/{id}

* _Insert data into master_

**POST** : /utilities/masterOfCards

* _Update data into master_

**POST** : /utilities/masterOfCards/update

* _Delete data from master_

**DELETE** : /utilities/masterOfCards/{id}

#### FM5-Headers <a href="#fm5-headers" id="fm5-headers"></a>

| Property     | Value            |
| ------------ | ---------------- |
| Content-type | application/json |
| Accept       | application/json |

### FM5-Available Properties <a href="#fm5-available-properties" id="fm5-available-properties"></a>

* cardCode
* cardBin
* cardName
* cardImage
* modeOfOperations
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

### FM5-Get All Data <a href="#fm5-get-all-data" id="fm5-get-all-data"></a>

This API endpoint helps you retrieve all the data objects stored in database with their unique Ids.

URL : /utilities/masterOfCards

Method Type : GET

> Response JSON

```
[{
  "cardCode": "string",
  "cardBin": "string",
  "cardName": "string",
  "cardImage": "string",
  "modeOfOperations": [
    "string"
  ],
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

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfCards?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}

### FM5-Find first matching result <a href="#fm5-find-first-matching-result" id="fm5-find-first-matching-result"></a>

This API endpoint helps you retrieve first data object matching the given properties, pass the filter argument in query, please see example url.

URL : /utilities/masterOfCards/findOne

Method Type : GET

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfCards/findOne?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}
>
> Response JSON

```
{
    "branchCode": "string",
    "branchName": "string",
    "branchAddress": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "pincode": "string",
    "region": "string",
    "id": "string"
  }
```

### FM5-Find by id <a href="#fm5-find-by-id" id="fm5-find-by-id"></a>

This API endpoint helps you retrieve data object matching unique object id, just pass the id replacing _{id}_ in the endpoint.

URL : /utilities/masterOfCards/{id}

Method Type : GET

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfCards/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
  "cardCode": "string",
  "cardBin": "string",
  "cardName": "string",
  "cardImage": "string",
  "modeOfOperations": [
    "string"
  ],
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

### FM5-Insert data into master <a href="#fm5-insert-data-into-master" id="fm5-insert-data-into-master"></a>

This API endpoint lets you save data object into the master, just hit the API with valid JSON object containing master's data.

URL : /utilities/masterOfCards

Method Type : POST

> Request JSON

```
{
  "cardCode": "string",
  "cardBin": "string",
  "cardName": "string",
  "cardImage": "string",
  "modeOfOperations": [
    "string"
  ],
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
  "cardCode": "string",
  "cardBin": "string",
  "cardName": "string",
  "cardImage": "string",
  "modeOfOperations": [
    "string"
  ],
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

### FM5-Delete from master <a href="#fm5-delete-from-master" id="fm5-delete-from-master"></a>

This API endpoint helps you delete data object matching unique object id, returns number of documents affected.

URL : /utilities/masterOfCards/{id}

Method Type : DELETE

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfCards/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
    "count": 1
}
```

### FM5-Update data into master <a href="#fm5-update-data-into-master" id="fm5-update-data-into-master"></a>

This API endpoint allows you to update all documents found by where filter with new values specified in body and returns number of documents modified.

URL : /utilities/masterOfCards/update

Method Type : POST

> Example URL with filter : https://indusind-dev.signzy.tech/utilities/masterOfCards/update?where={"property\_one": "value\_one","property\_two": "value\_two"}
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
