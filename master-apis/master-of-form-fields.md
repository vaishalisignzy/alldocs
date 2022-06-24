# Master Of Form Fields



Changes in this master are rendered as form fields on the form displayed in the flow.

#### FM7-Available HTTP Endpoints <a href="#fm7-available-http-endpoints" id="fm7-available-http-endpoints"></a>

* _Get all data_

**GET** : /utilities/masterOfFormFields

* _Find one_

**GET** : /utilities/masterOfFormFields/findOne

* _Find by id_

**GET** : /utilities/masterOfFormFields/{id}

* _Insert data into master_

**POST** : /utilities/masterOfFormFields

* _Update data into master_

**POST** : /utilities/masterOfFormFields/update

* _Delete data from master_

**DELETE** : /utilities/masterOfFormFields/{id}

#### FM7-Headers <a href="#fm7-headers" id="fm7-headers"></a>

| Property     | Value            |
| ------------ | ---------------- |
| Content-type | application/json |
| Accept       | application/json |

### FM7-Available Properties <a href="#fm7-available-properties" id="fm7-available-properties"></a>

* entityCode
* entityType
* fieldName
* fieldType
* displayText
* options
* sequence
* validations

### FM7- Mandatory -"fieldName" for Contract Generation.

| Mandatory - fieldName - Company+LLP+OPC + Partnership (Registered +Unregistered) |
| -------------------------------------------------------------------------------- |
| FREQ\_ALERT                                                                      |
| ESTAT\_FREQ                                                                      |
| pbPsCode                                                                         |
| remarks                                                                          |
| NATURE\_OF\_ACT                                                                  |
| noofemp                                                                          |
| GROSS\_ANNUAL\_INCOME                                                            |
| tranValue                                                                        |
| tranCount                                                                        |
| barcode                                                                          |

| Mandatory - fieldName -PROPRIETOR |
| --------------------------------- |
| FREQ\_ALERT                       |
| ESTAT\_FREQ                       |
| pbPsCode                          |
| remarks                           |
| NATURE\_OF\_ACT                   |
| noofemp                           |
| GROSS\_ANNUAL\_INCOME             |
| tranValue                         |
| tranCount                         |
| dateOfIncorp                      |
| barcode                           |

| I**NDIVIDUAL**       |
| -------------------- |
| FREQ\_ALERT          |
| ESTAT\_FREQ          |
| Resience\_Individual |
| barcode              |



### FM7- Non-Mandatory -"fieldName" (passed in finnacle)

| Company+LLP+OPC + Partnership (Registered +Unregistered) + Proprietor |
| --------------------------------------------------------------------- |
| trancheque                                                            |
| tranNRF                                                               |

### FM7- Possible Values- "fieldType**"**

* inputText,&#x20;
* inputNumber,&#x20;
* inputDate,&#x20;
* inputEmail,&#x20;
* inputPhone,&#x20;
* checkBox,&#x20;
* radioButton,&#x20;
* dropDown



### FM7-Get All Data <a href="#fm7-get-all-data" id="fm7-get-all-data"></a>

This API endpoint helps you retrieve all the data objects stored in database with their unique Ids.

URL : /utilities/masterOfFormFields

Method Type : GET

> Response JSON

```
[{
  "entityCode": "string",
  "entityType": "string",
  "fieldName": "string",
  "fieldType": "string",
  "displayText": "string",
  "options": [
    "string"
  ],
  "sequence": "string",
  "validations": "string",
  "id": "string"
}]
```

&#x20;You can also pass \`filter\` in query to get all instances matching particular properties.

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfFormFields?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}

### FM7-Find first matching result <a href="#fm7-find-first-matching-result" id="fm7-find-first-matching-result"></a>

This API endpoint helps you retrieve first data object matching the given properties, pass the filter argument in query, please see example url.

URL : /utilities/masterOfFormFields/findOne

Method Type : GET

> **Example URL with filter** : https://indusind-dev.signzy.tech/utilities/masterOfFormFields/findOne?filter={"where":{"property\_one": "value\_one"},{"property\_two": "value\_two"\}}
>
> Response JSON

```
{
  "entityCode": "string",
  "entityType": "string",
  "fieldName": "string",
  "fieldType": "string",
  "displayText": "string",
  "options": [
    "string"
  ],
  "sequence": "string",
  "validations": "string",
  "id": "string"
}
```

### FM7-Find by id <a href="#fm7-find-by-id" id="fm7-find-by-id"></a>

This API endpoint helps you retrieve data object matching unique object id, just pass the id replacing _{id}_ in the endpoint.

URL : /utilities/masterOfFormFields/{id}

Method Type : GET

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfFormFields/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
  "entityCode": "string",
  "entityType": "string",
  "fieldName": "string",
  "fieldType": "string",
  "displayText": "string",
  "options": [
    "string"
  ],
  "sequence": "string",
  "validations": "string",
  "id": "string"
}
```

### FM7-Insert data into master <a href="#fm7-insert-data-into-master" id="fm7-insert-data-into-master"></a>

This API endpoint lets you save data object into the master, just hit the API with valid JSON object containing master's data.

URL : /utilities/masterOfFormFields

Method Type : POST

> Request JSON

```
{
  "entityCode": "string",
  "entityType": "string",
  "fieldName": "string",
  "fieldType": "string",
  "displayText": "string",
  "options": [
    "string"
  ],
  "sequence": "string",
  "validations": "string"
}
```

> Response JSON

```
{
  "entityCode": "string",
  "entityType": "string",
  "fieldName": "string",
  "fieldType": "string",
  "displayText": "string",
  "options": [
    "string"
  ],
  "sequence": "string",
  "validations": "string",
  "id": "string"
}
```

### FM7-Delete from master <a href="#fm7-delete-from-master" id="fm7-delete-from-master"></a>

This API endpoint helps you delete data object matching unique object id, returns number of documents affected.

URL : /utilities/masterOfFormFields/{id}

Method Type : DELETE

> Example URL : https://indusind-dev.signzy.tech/utilities/masterOfFormFields/5b4ee6e18c1ae474e089648e
>
> Response JSON

```
{
    "count": 1
}
```

### FM7-Update data into master <a href="#fm7-update-data-into-master" id="fm7-update-data-into-master"></a>

This API endpoint allows you to update all documents found by where filter with new values specified in body and returns number of documents modified.

URL : /utilities/masterOfFormFields/update

Method Type : POST

> Example URL with filter : https://indusind-dev.signzy.tech/utilities/masterOfFormFields/update?where={"property\_one": "value\_one","property\_two": "value\_two"}
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
