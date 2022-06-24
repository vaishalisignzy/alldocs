# Master of Branch



Changes in this master are reflected on the form dropdowns (city, state, branch dropdowns) at create entity screen.

#### FM1-Available HTTP Endpoints <a href="#fm1-available-http-endpoints" id="fm1-available-http-endpoints"></a>

* _Get all data_

**GET** : /utilities/masterOfBranches

* _Find one_

**GET** : /utilities/masterOfBranches/findOne

* _Find by id_

**GET** : /utilities/masterOfBranches/{id}

* _Insert data into master_

**POST** : /utilities/masterOfBranches

* _Update data into master_

**POST** : /utilities/masterOfBranches/update

* _Delete data from master_

**DELETE** : /utilities/masterOfBranches/{id}

#### FM1-Headers <a href="#fm1-headers" id="fm1-headers"></a>

| Property     | Value            |
| ------------ | ---------------- |
| Content-type | application/json |
| Accept       | application/json |

### FM1-Available Properties <a href="#fm1-available-properties" id="fm1-available-properties"></a>

* branchcode
* branchName
* branchAddress
* city
* state
* country
* pincode
*   region\
    &#x20;

    ![](https://docs.google.com/a/signzy.com/drawings/d/s7ra3MHIrFiGKwtpFHc7rEw/image?w=485\&h=570\&rev=42\&ac=1\&parent=1bj6XdXh9aqjwlWRgAcCYzupCPl8MiI2qebMj-zRTPi4)

    &#x20;



### FM1-Get All Data <a href="#fm1-get-all-data" id="fm1-get-all-data"></a>

This API endpoint helps you retrieve all the data objects stored in database with their unique Ids.

URL : /utilities/masterOfBranches

Method Type : GET

> Response JSON

```
[{
    "branchCode": "string",
    "branchName": "string",
    "branchAddress": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "pincode": "string",
    "region": "string",
    "id": "string"
}]
```

&#x20;You can also pass \`filter\` in query to get all instances matching particular properties.

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfBranches?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}

### FM1-Find first matching result <a href="#fm1-find-first-matching-result" id="fm1-find-first-matching-result"></a>

This API endpoint helps you retrieve first data object matching the given properties, pass the filter argument in query, please see example url.

URL : /utilities/masterOfBranches/findOne

Method Type : GET

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfBranches/findOne?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}
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

### FM1-Find by id <a href="#fm1-find-by-id" id="fm1-find-by-id"></a>

This API endpoint helps you retrieve data object matching unique object id, just pass the id replacing _{id}_ in the endpoint.

URL : /utilities/masterOfBranches/{id}

Method Type : GET

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfBranches/5b4ee6e18c1ae474e089648e
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

### FM1-Insert data into master <a href="#fm1-insert-data-into-master" id="fm1-insert-data-into-master"></a>

This API endpoint lets you save data object into the master, just hit the API with valid JSON object containing master's data.

URL : /utilities/masterOfBranches

Method Type : POST

> Request JSON

```
{
    "branchCode": "string",
    "branchName": "string",
    "branchAddress": "string",
    "city": "string",
    "state": "string",
    "country": "string",
    "pincode": "string",
    "region": "string"
  }
```

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

### FM1-Delete from master <a href="#fm1-delete-from-master" id="fm1-delete-from-master"></a>

This API endpoint helps you delete data object matching unique object id, returns number of documents affected.

URL : /utilities/masterOfBranches/{id}

Method Type : DELETE

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfBranches/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
    "count": 1
}
```

### FM1-Update data into master <a href="#fm1-update-data-into-master" id="fm1-update-data-into-master"></a>

This API endpoint allows you to update all documents found by where filter with new values specified in body and returns number of documents modified.

URL : /utilities/masterOfBranches/update

Method Type : POST

> Example URL with filter : https://indusind-dev.signzy.tech/utilities/masterOfBranches/update?where={"property\_one": "value\_one","property\_two": "value\_two"}
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
