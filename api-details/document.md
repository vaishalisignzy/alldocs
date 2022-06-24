# Document

## Create Document

#### Input Headers for Create Document <a href="#input-headers-for-create-document" id="input-headers-for-create-document"></a>

| Property      | Value                                     |
| ------------- | ----------------------------------------- |
| Content-type  | application/json                          |
| Authorisation | Authorization header as per login request |

```
{
  "merchantId": "Merchant id",
  "tagId":"Tag id",
  "docType": "idCard/roc/nonRoc/video/contract",
  "docSubType": "document specific type like aadhaar/gstn",
  "name":"Name of the document it is to be identified by"
}
```

#### Input for Create Document <a href="#input-for-create-document" id="input-for-create-document"></a>

Post request to: **/engine/merchants/:merchantId/tags/createDocument** Below table describes all the properties available in the request body.

| Property   | Accepted values/format | Description                            |
| ---------- | ---------------------- | -------------------------------------- |
| merchantId | String                 | id of the Merchant, the tag belongs to |
| tagId      | String                 | id of the Tag, the document belongs to |
| docType    | String                 | Valid type of the document             |
| docSubType | String                 | Valid subType of the document          |
| name       | String                 | Common identifier of the document      |

_Document will be executed only for specific docType and docSubType supported by the Signzy system. You can enter anything as the type and subType if the document need not be executed. You cannot change the docType and docSubType at a later stage._

#### Expected Response <a href="#expected-response" id="expected-response"></a>

```
{
    "result": {
        "result": "Document Created",
        "documentId": "Documnet Unique alphanumeric id"
    }
}
```

| Property   | Accepted values/format | Description                                |
| ---------- | ---------------------- | ------------------------------------------ |
| result     | Object                 | Object Document created or error           |
| documentId | String                 | The id of the Merchant, the tag belongs to |

### Execute Document <a href="#execute-document" id="execute-document"></a>

#### Input Headers for Execute Document <a href="#input-headers-for-execute-document" id="input-headers-for-execute-document"></a>

| Property      | Value                                     |
| ------------- | ----------------------------------------- |
| Content-type  | application/json                          |
| Authorisation | Authorization header as per login request |

```
{
  "merchantId": "Merchant id",
  "tagId":"Tag id",
  "documentId":"Document id returned from create document",
  "images": "Array of images to be extracted",
  "formData": "JSON Object of all required fields"
}
```

#### Input for Execute Document <a href="#input-for-execute-document" id="input-for-execute-document"></a>

Post request to: **/engine/merchants/:merchantId/tags/executeDocument** Below table describes all the properties available in the request body.

| Property   | Accepted values/format | Description                                                        |
| ---------- | ---------------------- | ------------------------------------------------------------------ |
| merchantId | String                 | id of the Merchant, the tag belongs to                             |
| tagId      | String                 | id of the Tag, the document belongs to                             |
| documentId | String                 | Document id returned from create document                          |
| images     | Array of image urls    | Array of image urls required to execute the document               |
| formData   | Object                 | JSON Object of all required fields for that docType and docSubType |

#### Expected Response <a href="#expected-response-2" id="expected-response-2"></a>

```
{
    "result": {
        "result": "Document Created",
        "documentId": "Documnet Unique alphanumeric id"
    }
}
```

| Property   | Accepted values/format | Description                                |
| ---------- | ---------------------- | ------------------------------------------ |
| result     | Object                 | Object containg teh output of execution    |
| documentId | String                 | The id of the Merchant, the tag belongs to |

#### Accepted Values for docType and docSubType <a href="#accepted-values-for-doctype-and-docsubtype" id="accepted-values-for-doctype-and-docsubtype"></a>

| docType | docSubType          |
| ------- | ------------------- |
| idCard  | aadhaar             |
| idCard  | individualPan       |
| idCard  | businessPan         |
| idCard  | passport            |
| idCard  | drivingLicence      |
| idCard  | cheque              |
| roc     | simpleSearchByCin   |
| roc     | quickSearchByCin    |
| roc     | detailedSearchByCin |
| nonRoc  | iec                 |
| nonRoc  | tin                 |
| nonRoc  | centralServiceTax   |
| nonRoc  | sec                 |
| nonRoc  | ptr                 |
| nonRoc  | gstn                |
| nonRoc  | icai                |
| nonRoc  | icsi                |
| nonRoc  | icwai               |
| nonRoc  | mci                 |
| nonRoc  | tan                 |
| nonRoc  | fssai               |
| nonRoc  | uam                 |

### Save Document <a href="#save-document" id="save-document"></a>

#### Input Headers for Save Document <a href="#input-headers-for-save-document" id="input-headers-for-save-document"></a>

| Property      | Value                                     |
| ------------- | ----------------------------------------- |
| Content-type  | application/json                          |
| Authorisation | Authorization header as per login request |

```
{
  "merchantId": "Merchant id",
  "tagId":"Tag id",
  "documentId":"Document id returned from create document",
  "images": "Array of images to be saved",
  "formData": "JSON Object of all fields that ypu want to save"
}
```

#### Input for Save Document <a href="#input-for-save-document" id="input-for-save-document"></a>

Post request to: **/engine/merchants/:merchantId/tags/saveDocument** Below table describes all the properties available in the request body.

| Property   | Accepted values/format | Description                                                        |
| ---------- | ---------------------- | ------------------------------------------------------------------ |
| merchantId | String                 | id of the Merchant, the tag belongs to                             |
| tagId      | String                 | id of the Tag, the document belongs to                             |
| documentId | String                 | Document id returned from create document                          |
| images     | Array of image urls    | Array of image urls required to execute the document               |
| formData   | Object                 | JSON Object of all required fields for that docType and docSubType |

**The formData field of input must contain a toVerify string field. The possible values of toVerify string are "Verify by Signzy", "Already Verified", "Do not Verify". This field is impprtant because it will determine if the document is verified by the verification engine when the call VE request is sent. Only documents with "Verify by Signzy" as the toVerify field will be verified. The default value is "Verify by Signzy".**

#### Expected Response <a href="#expected-response-3" id="expected-response-3"></a>

```
{
    "result": {
        "result": "Document Created",
        "documentId": "Documnet Unique alphanumeric id"
    }
}
```

| Property   | Accepted values/format | Description                                |
| ---------- | ---------------------- | ------------------------------------------ |
| result     | Object                 | Object Document created or error           |
| documentId | String                 | The id of the Merchant, the tag belongs to |

### Delete Document <a href="#delete-document" id="delete-document"></a>

#### Input Headers for Delete Document <a href="#input-headers-for-delete-document" id="input-headers-for-delete-document"></a>

| Property      | Value                                     |
| ------------- | ----------------------------------------- |
| Content-type  | application/json                          |
| Authorisation | Authorization header as per login request |

```
{
  "merchantId": "Merchant id",
  "tagId":"Tag id",
  "documentId":"Document id returned from create document"
}
```

#### Input for Delete Document <a href="#input-for-delete-document" id="input-for-delete-document"></a>

Post request to: **/engine/merchants/:merchantId/tags/deleteDocument** Below table describes all the properties available in the request body.

| Property   | Accepted values/format | Description                               |
| ---------- | ---------------------- | ----------------------------------------- |
| merchantId | String                 | id of the Merchant, the tag belongs to    |
| tagId      | String                 | id of the Tag, the document belongs to    |
| documentId | String                 | Document id returned from create document |

#### Expected Response <a href="#expected-response-4" id="expected-response-4"></a>

```
{
    "result": {
        "result": "Document Created",
        "documentId": "Documnet Unique alphanumeric id"
    }
}
```

| Property   | Accepted values/format | Description                                |
| ---------- | ---------------------- | ------------------------------------------ |
| result     | Object                 | Object Document created or error           |
| documentId | String                 | The id of the Merchant, the tag belongs to |
