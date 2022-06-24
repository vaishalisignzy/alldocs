# Master Of Field Verification Criteria



This master is used for defining field verification critera which in turn is used for assigning field verification agency, if the customer matches the critera defined in this master an email is sent to the field verification agency for offline verification of the customer.

#### BM1-Available HTTP Endpoints <a href="#bm1-available-http-endpoints" id="bm1-available-http-endpoints"></a>

* _Get all data_

**GET** : /utilities/criteriaOfFvs

* _Find one_

**GET** : /utilities/criteriaOfFvs/findOne

* _Find by id_

**GET** : /utilities/criteriaOfFvs/{id}

* _Insert data into master_

**POST** : /utilities/criteriaOfFvs

* _Update data into master_

**POST** : /utilities/criteriaOfFvs/update

* _Delete data from master_

**DELETE** : /utilities/criteriaOfFvs/{id}

#### BM1-Headers <a href="#bm1-headers" id="bm1-headers"></a>

| Property     | Value            |
| ------------ | ---------------- |
| Content-type | application/json |
| Accept       | application/json |

### BM1-Available Properties <a href="#bm1-available-properties" id="bm1-available-properties"></a>

* fvCriteriaNumber
* entityType
* entityCode
* poaCommunication
* poiAuthorizedSignatory
* poaAuthorizedSignatoryPermanent
* poaAuthorizedSignatoryCommunication
* declarationCode
* natureOfBusiness
* pinCode
* amlCheckFlag
* excludedProductCode

### BM1-Get All Data <a href="#bm1-get-all-data" id="bm1-get-all-data"></a>

This API endpoint helps you retrieve all the data objects stored in database with their unique Ids.

URL : /utilities/criteriaOfFvs

Method Type : GET

> Response JSON

```
[{
  "fvCriteriaNumber": "string",
  "entityType": "string",
  "entityCode": "string",
  "poaCommunication": "string",
  "poiAuthorizedSignatory": "string",
  "poaAuthorizedSignatoryPermanent": "string",
  "poaAuthorizedSignatoryCommunication": "string",
  "declarationCode": "string",
  "natureOfBusiness": "string",
  "pinCode": "string",
  "amlCheckFlag": "string",
  "excludedProductCode": "string",
  "id": "string"
}]
```

&#x20;You can also pass \`filter\` in query to get all instances matching particular properties.

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/criteriaOfFvs?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}

### BM1-Find first matching result <a href="#bm1-find-first-matching-result" id="bm1-find-first-matching-result"></a>

This API endpoint helps you retrieve first data object matching the given properties, pass the filter argument in query, please see example url.

URL : /utilities/criteriaOfFvs/findOne

Method Type : GET

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/criteriaOfFvs/findOne?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}
>
> Response JSON

```
{
  "fvCriteriaNumber": "string",
  "entityType": "string",
  "entityCode": "string",
  "poaCommunication": "string",
  "poiAuthorizedSignatory": "string",
  "poaAuthorizedSignatoryPermanent": "string",
  "poaAuthorizedSignatoryCommunication": "string",
  "declarationCode": "string",
  "natureOfBusiness": "string",
  "pinCode": "string",
  "amlCheckFlag": "string",
  "excludedProductCode": "string",
  "id": "string"
}
```

### BM1-Find by id <a href="#bm1-find-by-id" id="bm1-find-by-id"></a>

This API endpoint helps you retrieve data object matching unique object id, just pass the id replacing _{id}_ in the endpoint.

URL : /utilities/criteriaOfFvs/{id}

Method Type : GET

> Example URL : https://indusind-dev.signzy.tech/utilities/criteriaOfFvs/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
  "fvCriteriaNumber": "string",
  "entityType": "string",
  "entityCode": "string",
  "poaCommunication": "string",
  "poiAuthorizedSignatory": "string",
  "poaAuthorizedSignatoryPermanent": "string",
  "poaAuthorizedSignatoryCommunication": "string",
  "declarationCode": "string",
  "natureOfBusiness": "string",
  "pinCode": "string",
  "amlCheckFlag": "string",
  "excludedProductCode": "string",
  "id": "string"
}
```

### BM1-Insert data into master <a href="#bm1-insert-data-into-master" id="bm1-insert-data-into-master"></a>

This API endpoint lets you save data object into the master, just hit the API with valid JSON object containing master's data.

URL : /utilities/criteriaOfFvs

Method Type : POST

> Request JSON

```
{
  "fvCriteriaNumber": "string",
  "entityType": "string",
  "entityCode": "string",
  "poaCommunication": "string",
  "poiAuthorizedSignatory": "string",
  "poaAuthorizedSignatoryPermanent": "string",
  "poaAuthorizedSignatoryCommunication": "string",
  "declarationCode": "string",
  "natureOfBusiness": "string",
  "pinCode": "string",
  "amlCheckFlag": "string",
  "excludedProductCode": "string"
}
```

> Response JSON

```
{
  "fvCriteriaNumber": "string",
  "entityType": "string",
  "entityCode": "string",
  "poaCommunication": "string",
  "poiAuthorizedSignatory": "string",
  "poaAuthorizedSignatoryPermanent": "string",
  "poaAuthorizedSignatoryCommunication": "string",
  "declarationCode": "string",
  "natureOfBusiness": "string",
  "pinCode": "string",
  "amlCheckFlag": "string",
  "excludedProductCode": "string",
  "id": "string"
}
```

### BM1-Delete from master <a href="#bm1-delete-from-master" id="bm1-delete-from-master"></a>

This API endpoint helps you delete data object matching unique object id, returns number of documents affected.

URL : /utilities/criteriaOfFvs/{id}

Method Type : DELETE

> Example URL : https://indusind-dev.signzy.tech/utilities/criteriaOfFvs/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
    "count": 1
}
```

### BM1-Update data into master <a href="#bm1-update-data-into-master" id="bm1-update-data-into-master"></a>

This API endpoint allows you to update all documents found by where filter with new values specified in body and returns number of documents modified.

URL : /utilities/criteriaOfFvs/update

Method Type : POST

> Example URL with filter : https://indusind-dev.signzy.tech/utilities/criteriaOfFvs/update?where={"property\_one": "value\_one","property\_two": "value\_two"}
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
