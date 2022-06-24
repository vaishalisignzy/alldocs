# Master Of Green Channel Matrix



This master is used to define criteria which in turn decides whether the data collected will go to the iWorks or iWorks and finacle both.

#### BM4-Available HTTP Endpoints <a href="#bm4-available-http-endpoints" id="bm4-available-http-endpoints"></a>

* _Get all data_

**GET** : /utilities/greenChannelMatrices

* _Find one_

**GET** : /utilities/greenChannelMatrices/findOne

* _Find by id_

**GET** : /utilities/greenChannelMatrices/{id}

* _Insert data into master_

**POST** : /utilities/greenChannelMatrices

* _Update data into master_

**POST** : /utilities/greenChannelMatrices/update

* _Delete data from master_

**DELETE** : /utilities/greenChannelMatrices/{id}

#### BM4-Headers <a href="#bm4-headers" id="bm4-headers"></a>

| Property     | Value            |
| ------------ | ---------------- |
| Content-type | application/json |
| Accept       | application/json |

### BM4-Available Properties <a href="#bm4-available-properties" id="bm4-available-properties"></a>

* entityCode
* entityType
* proofOfExistence2
* poaRegistered
* poaCommunication
* poiAuthorizedSignatory
* poaAuthorizedSignatory
* poaAuthorizedSignatoryCommunication
* crilicMatch
* pennyDropMatching
* fvCheck
* amlCheck
* greenChannel
* freezeStatus

### Possible Values

* **entityType** :  "COMPANY", "LIMITED LIABILITY PARTNERSHIP", "ONE PERSON COMPANY", "PROPRIETOR", "INDIVIDUAL", "REGISTERED PARTNERSHIP", "UNREGISTERED PARTNERSHIP"
* **crilicMatch** : "SUCCESS", "FAIL" (SUCCESS means individual/ entity has successfully passed the test).
* **proofOfExistence2 :** "blank", "weak", "strong"
* **poaRegistered** : "blank", "weak", "strong"
* **poaCommunication :** "blank", "weak", "strong"
* **poiAuthorizedSignatory : "**blank", "weak", "strong"
* **poaAuthorizedSignatory :** "blank", "weak", "strong"
* **poaAuthorizedSignatoryCommunication** : "blank", "weak", "strong"
* **pennyDropMatching :** true, false
* **fvCheck** : true, false (true means record is found in database)
* **amlCheck :** "SUCCESS", "FAIL" (SUCCESS means individual/ entity has successfully passed the test).

### BM4-Get All Data <a href="#bm4-get-all-data" id="bm4-get-all-data"></a>

This API endpoint helps you retrieve all the data objects stored in database with their unique Ids.

URL : /utilities/greenChannelMatrices

Method Type : GET

> Response JSON

```
[{
  "entityCode": "string",
  "entityType": "string",
  "proofOfExistence2": "string",
  "poaRegistered": "string",
  "poaCommunication": "string",
  "poiAuthorizedSignatory": "string",
  "poaAuthorizedSignatory": "string",
  "poaAuthorizedSignatoryCommunication": "string",
  "crilicMatch": "string",
  "pennyDropMatching": boolean,
  "fvCheck": boolean,
  "amlCheck": "string",
  "greenChannel": "string",
  "freezeStatus": "string",
  "id": "string"
}]
```

&#x20;You can also pass \`filter\` in query to get all instances matching particular properties.

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/greenChannelMatrices?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}

### BM4-Find first matching result <a href="#bm4-find-first-matching-result" id="bm4-find-first-matching-result"></a>

This API endpoint helps you retrieve first data object matching the given properties, pass the filter argument in query, please see example url.

URL : /utilities/greenChannelMatrices/findOne

Method Type : GET

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/greenChannelMatrices/findOne?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}
>
> Response JSON

```
{
  "entityCode": "string",
  "entityType": "string",
  "proofOfExistence2": "string",
  "poaRegistered": "string",
  "poaCommunication": "string",
  "poiAuthorizedSignatory": "string",
  "poaAuthorizedSignatory": "string",
  "poaAuthorizedSignatoryCommunication": "string",
  "crilicMatch": "string",
  "pennyDropMatching": boolean,
  "fvCheck": boolean,
  "amlCheck": "string",
  "greenChannel": "string",
  "freezeStatus": "string",
  "id": "string"
}
```

### BM4-Find by id <a href="#bm4-find-by-id" id="bm4-find-by-id"></a>

This API endpoint helps you retrieve data object matching unique object id, just pass the id replacing _{id}_ in the endpoint.

URL : /utilities/greenChannelMatrices/{id}

Method Type : GET

> Example URL : https://indusind-dev.signzy.tech/utilities/greenChannelMatrices/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
  "entityCode": "string",
  "entityType": "string",
  "proofOfExistence2": "string",
  "poaRegistered": "string",
  "poaCommunication": "string",
  "poiAuthorizedSignatory": "string",
  "poaAuthorizedSignatory": "string",
  "poaAuthorizedSignatoryCommunication": "string",
  "crilicMatch": "string",
  "pennyDropMatching": boolean,
  "fvCheck": boolean,
  "amlCheck": "string",
  "greenChannel": "string",
  "freezeStatus": "string",
  "id": "string"
}
```

### BM4-Insert data into master <a href="#bm4-insert-data-into-master" id="bm4-insert-data-into-master"></a>

This API endpoint lets you save data object into the master, just hit the API with valid JSON object containing master's data.

URL : /utilities/greenChannelMatrices

Method Type : POST

> Request JSON

```
{
  "entityCode": "string",
  "entityType": "string",
  "proofOfExistence2": "string",
  "poaRegistered": "string",
  "poaCommunication": "string",
  "poiAuthorizedSignatory": "string",
  "poaAuthorizedSignatory": "string",
  "poaAuthorizedSignatoryCommunication": "string",
  "crilicMatch": "string",
  "pennyDropMatching": boolean,
  "fvCheck": boolean,
  "amlCheck": "string",
  "greenChannel": "string",
  "freezeStatus": "string"
}
```

> Response JSON

```
{
  "entityCode": "string",
  "entityType": "string",
  "proofOfExistence2": "string",
  "poaRegistered": "string",
  "poaCommunication": "string",
  "poiAuthorizedSignatory": "string",
  "poaAuthorizedSignatory": "string",
  "poaAuthorizedSignatoryCommunication": "string",
  "crilicMatch": "string",
  "pennyDropMatching": boolean,
  "fvCheck": boolean,
  "amlCheck": "string",
  "greenChannel": "string",
  "freezeStatus": "string",
  "id": "string"
}
```

### BM4-Delete from master <a href="#bm4-delete-from-master" id="bm4-delete-from-master"></a>

This API endpoint helps you delete data object matching unique object id, returns number of documents affected.

URL : /utilities/greenChannelMatrices/{id}

Method Type : DELETE

> Example URL : https://indusind-dev.signzy.tech/utilities/greenChannelMatrices/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
    "count": 1
}
```

### BM4-Update data into master <a href="#bm4-update-data-into-master" id="bm4-update-data-into-master"></a>

This API endpoint allows you to update all documents found by where filter with new values specified in body and returns number of documents modified.

URL : /utilities/greenChannelMatrices/update

Method Type : POST

> Example URL with filter : https://indusind-dev.signzy.tech/utilities/greenChannelMatrices/update?where={"property\_one": "value\_one","property\_two": "value\_two"}
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
