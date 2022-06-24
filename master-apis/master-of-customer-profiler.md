# Master Of Customer Profiler



This master is used to define criteria which in turn decides what products are shown on the recommended products page.

#### BM3-Available HTTP Endpoints <a href="#bm3-available-http-endpoints" id="bm3-available-http-endpoints"></a>

* _Get all data_

**GET** : /utilities/masterOfCustomerProfilers

* _Find one_

**GET** : /utilities/masterOfCustomerProfilers/findOne

* _Find by id_

**GET** : /utilities/masterOfCustomerProfilers/{id}

* _Insert data into master_

**POST** : /utilities/masterOfCustomerProfilers

* _Update data into master_

**POST** : /utilities/masterOfCustomerProfilers/update

* _Delete data from master_

**DELETE** : /utilities/masterOfCustomerProfilers/{id}

#### BM3-Headers <a href="#bm3-headers" id="bm3-headers"></a>

| Property     | Value            |
| ------------ | ---------------- |
| Content-type | application/json |
| Accept       | application/json |

### BM3-Available Properties <a href="#bm3-available-properties" id="bm3-available-properties"></a>

* vintageYears
* typeOfBusiness
* constitution
* industry
* turnover
* productCode

### Description- Properties&#x20;

* vintageYears :- Difference between Current Date and date of incorporation.
* typeOfBusiness :- It is business type selected by RM on the app, it corresponds to "remarks" field in finnacle and "remarks" field in "Master of Form Fields".
* constitution:- It is the entity type selected by RM on front-end
* industry:- It is the industry type selected by RM on the app. It corresponds to "NATURE\_OF\_ACT" field in "Master of Form Fields" and "industry" field in finnacle corporation.
* turnover:-  It is the annual turnover of the Entity, which corresponds to "GROSS\_ANNUAL\_INCOME" field in finnacle and "Master of Form Fields".
* productCode :- These are the codes of the products which will be shown on the front- end basis the above data filled by RM.

### BM3-Get All Data <a href="#bm3-get-all-data" id="bm3-get-all-data"></a>

This API endpoint helps you retrieve all the data objects stored in database with their unique Ids.

URL : /utilities/masterOfCustomerProfilers

Method Type : GET

> Response JSON

```
[{
  "vintageYears": "string",
  "typeOfBusiness": "string",
  "constitution": "string",
  "industry": "string",
  "turnover": "string",
  "productCode": "string",
  "id": "string"
}]
```

&#x20;You can also pass \`filter\` in query to get all instances matching particular properties.

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfCustomerProfilers?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}

### BM3-Find first matching result <a href="#bm3-find-first-matching-result" id="bm3-find-first-matching-result"></a>

This API endpoint helps you retrieve first data object matching the given properties, pass the filter argument in query, please see example url.

URL : /utilities/masterOfCustomerProfilers/findOne

Method Type : GET

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfCustomerProfilers/findOne?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}
>
> Response JSON

```
{
  "vintageYears": "string",
  "typeOfBusiness": "string",
  "constitution": "string",
  "industry": "string",
  "turnover": "string",
  "productCode": "string",
  "id": "string"
}
```

### BM3-Find by id <a href="#bm3-find-by-id" id="bm3-find-by-id"></a>

This API endpoint helps you retrieve data object matching unique object id, just pass the id replacing _{id}_ in the endpoint.

URL : /utilities/masterOfCustomerProfilers/{id}

Method Type : GET

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfCustomerProfilers/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
  "vintageYears": "string",
  "typeOfBusiness": "string",
  "constitution": "string",
  "industry": "string",
  "turnover": "string",
  "productCode": "string",
  "id": "string"
}
```

### BM3-Insert data into master <a href="#bm3-insert-data-into-master" id="bm3-insert-data-into-master"></a>

This API endpoint lets you save data object into the master, just hit the API with valid JSON object containing master's data.

URL : /utilities/masterOfCustomerProfilers

Method Type : POST

> Request JSON

```
{
  "vintageYears": "string",
  "typeOfBusiness": "string",
  "constitution": "string",
  "industry": "string",
  "turnover": "string",
  "productCode": "string"
}
```

> Response JSON

```
{
  "vintageYears": "string",
  "typeOfBusiness": "string",
  "constitution": "string",
  "industry": "string",
  "turnover": "string",
  "productCode": "string",
  "id": "string"
}
```

### BM3-Delete from master <a href="#bm3-delete-from-master" id="bm3-delete-from-master"></a>

This API endpoint helps you delete data object matching unique object id, returns number of documents affected.

URL : /utilities/masterOfCustomerProfilers/{id}

Method Type : DELETE

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfCustomerProfilers/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
    "count": 1
}
```

### BM3-Update data into master <a href="#bm3-update-data-into-master" id="bm3-update-data-into-master"></a>

This API endpoint allows you to update all documents found by where filter with new values specified in body and returns number of documents modified.

URL : /utilities/masterOfCustomerProfilers/update

Method Type : POST

> Example URL with filter : https://indusind-dev.signzy.tech/utilities/masterOfCustomerProfilers/update?where={"property\_one": "value\_one","property\_two": "value\_two"}
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
