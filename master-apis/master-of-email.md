# Master Of Email

This api is used to update interval and frequency of the emails sent by scheduler.

#### BM7-Available HTTP Endpoints <a href="#bm7-available-http-endpoints" id="bm7-available-http-endpoints"></a>

* _Get all data_

**GET** : /utilities/masterOfEmails

* _Find one_

**GET** : /utilities/masterOfEmails/findOne

* _Find by id_

**GET** : /utilities/masterOfEmails/{id}

* _Insert data into master_

**POST** : /utilities/masterOfEmails

* _Update data into master_

**POST** : /utilities/masterOfEmails/update

* _Delete data from master_

**DELETE** : /utilities/masterOfEmails/{id}

#### BM7-Headers <a href="#bm7-headers" id="bm7-headers"></a>

| Property     | Value            |
| ------------ | ---------------- |
| Content-type | application/json |
| Accept       | application/json |

### BM7-Available Properties <a href="#bm7-available-properties" id="bm7-available-properties"></a>

* frequency
* interval

### BM7-Description  <a href="#bm7-available-properties" id="bm7-available-properties"></a>

* frequency:- How many times "Reminder E-mails and SMSs" need to be send.
* interval :-  Difference between subsequent E-mails in days.&#x20;

### BM7-Get All Data <a href="#bm7-get-all-data" id="bm7-get-all-data"></a>

This API endpoint helps you retrieve all the data objects stored in database with their unique Ids.

URL : /utilities/masterOfEmails

Method Type : GET

> Response JSON

```
[{
    "frequency": "string",
    "interval": "string",
    "id": "string"
}]
```

&#x20;You can also pass \`filter\` in query to get all instances matching particular properties.

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfEmails?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}

### BM7-Find first matching result <a href="#bm7-find-first-matching-result" id="bm7-find-first-matching-result"></a>

This API endpoint helps you retrieve first data object matching the given properties, pass the filter argument in query, please see example url.

URL : /utilities/masterOfEmails/findOne

Method Type : GET

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfEmails/findOne?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}
>
> Response JSON

```
{
    "frequency": "string",
    "interval": "string",
    "id": "string"
}
```

### BM7-Find by id <a href="#bm7-find-by-id" id="bm7-find-by-id"></a>

This API endpoint helps you retrieve data object matching unique object id, just pass the id replacing _{id}_ in the endpoint.

URL : /utilities/masterOfEmails/{id}

Method Type : GET

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfEmails/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
    "frequency": "string",
    "interval": "string",
    "id": "string"
}
```

### BM7-Insert data into master <a href="#bm7-insert-data-into-master" id="bm7-insert-data-into-master"></a>

This API endpoint lets you save data object into the master, just hit the API with valid JSON object containing master's data.

URL : /utilities/masterOfEmails

Method Type : POST

> Request JSON

```
{
    "frequency": "string",
    "interval": "string",
}
```

> Response JSON

```
{
    "frequency": "string",
    "interval": "string",
    "id": "string"
}
```

### BM7-Delete from master <a href="#bm7-delete-from-master" id="bm7-delete-from-master"></a>

This API endpoint helps you delete data object matching unique object id, returns number of documents affected.

URL : /utilities/masterOfEmails/{id}

Method Type : DELETE

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfEmails/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
    "count": 1
}
```

### BM7-Update data into master <a href="#bm7-update-data-into-master" id="bm7-update-data-into-master"></a>

This API endpoint allows you to update all documents found by where filter with new values specified in body and returns number of documents modified.

URL : /utilities/masterOfEmails/update

Method Type : POST

> Example URL with filter : https://indusind-dev.signzy.tech/utilities/masterOfEmails/update?where={"property\_one": "value\_one","property\_two": "value\_two"}
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
