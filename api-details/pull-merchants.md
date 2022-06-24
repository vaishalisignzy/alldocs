# Pull merchants

### Pull Merchant by Customer <a href="#pull-merchant-by-customer" id="pull-merchant-by-customer"></a>

#### Input headers <a href="#input-headers" id="input-headers"></a>

| Property      | Value                                     |
| ------------- | ----------------------------------------- |
| Content-type  | application/json                          |
| Authorisation | Authorization header as per login request |

```
{
  "customerId": "Customer's valid Id",
  "status": "accepted/rejected/pending/all"
}
```

#### Input for Pull Merchant by Customer <a href="#input-for-pull-merchant-by-customer" id="input-for-pull-merchant-by-customer"></a>

Post request to: **/engine/pullmerchants**

Below table describes all the properties available in the request body.

| Property   | Accepted values/format | Description                                               |
| ---------- | ---------------------- | --------------------------------------------------------- |
| customerId | String                 | The id of the Customer you want to pull all merchants for |

#### Expected Response <a href="#expected-response" id="expected-response"></a>

```
{
  "result": "Array of all Merchants belonging to the Customer with the specified status"
}
```

| Property | Accepted values/format | Description                                                                |
| -------- | ---------------------- | -------------------------------------------------------------------------- |
| result   | Object                 | Array of all Merchants belonging to the Customer with the specified status |

### Pull Merchant by Id <a href="#pull-merchant-by-id" id="pull-merchant-by-id"></a>

#### Input headers <a href="#input-headers-2" id="input-headers-2"></a>

| Property      | Value                                     |
| ------------- | ----------------------------------------- |
| Content-type  | application/json                          |
| Authorisation | Authorization header as per login request |

```
{
  "customerId": "Customer's valid Id",
  "merchantId": "Merchant's valid Id"
}
```

#### Input for Pull Merchant by Customer <a href="#input-for-pull-merchant-by-customer-2" id="input-for-pull-merchant-by-customer-2"></a>

Post request to: **/engine/pullmerchants**

Below table describes all the properties available in the request body.

| Property   | Accepted values/format | Description                                               |
| ---------- | ---------------------- | --------------------------------------------------------- |
| customerId | String                 | The id of the Customer you want to pull all merchants for |
| merchantId | String                 | The id of the Merchant you want to pull                   |

#### Expected Response <a href="#expected-response-2" id="expected-response-2"></a>

```
{
            "_id": "5c2f3a942abe843e6129fc4e",
            "email": "qragati@signzy.com",
            "phone": "9970876543",
            "name": "Pragati Garg",
            "username": "qragati",
            "customerId": "5c265518a0a91171b2c945ba",
            "password": "$2a$10$18HBR2jFu2p4IZkBAWXDeeT.tBwPleSNKYbodtkvWCCbzkyZP09QO",
            "status": "pending",
            "verificationData": {},
            "verificationResult": {},
            "adminId": "",
            "adminName": "",
            "adminUsername": "",
            "redirectUrl": null,
            "tagLimit": 2,
            "documentLimit": 2,
            "grants": {
                "idCard": {
                    "aadhaar": {
                        "autoRecognition": true,
                        "verification": true
                    },
                    "individualPan": {
                        "autoRecognition": true,
                        "verification": true
                    },
                    "businessPan": {
                        "autoRecognition": true,
                        "verification": true
                    },
                    "passport": {
                        "autoRecognition": true,
                        "verification": true
                    },
                    "drivingLicence": {
                        "autoRecognition": true,
                        "verification": true
                    },
                    "cheque": {
                        "autoRecognition": true,
                        "verification": true
                    }
                },
                "roc": {
                    "quickSearchByCin": true,
                    "simpleSearchByCin": true,
                    "detailedSearchByCin": true
                },
                "nonRoc": {
                    "iec": true,
                    "tin": true,
                    "centralServiceTax": true,
                    "sec": true,
                    "ptr": true,
                    "gstn": true,
                    "uam": true,
                    "icai": true,
                    "icsi": true,
                    "icwai": true,
                    "mci": true,
                    "tan": true,
                    "fssai": true
                },
                "video": true,
                "contract": true
            },
            "accessToken": "eYdUkrZsUuv4vIh7kiPV0He1xUbhoXBQkCv8zgVZEAFzIBt478RFPZDvQDkGA8Hj",
            "merchantId": "5c2f3a942abe843e6129fc4e",
            "accessTokenUser": "j02DDTuAxuBGcW4sh7eAjN9k9qj3abl1fz78CogFvhN0dlpGe1lHBxfor4JLHY8q",
            "accessTokenEsign": "XIizUzanXV51DNChknY55C55Bjr7eHsnlsUfPEdycijCyjmnqBHR3cQHyebRoH98",
            "esignId": "5b238efe417669792eaddf1d",
            "userId": "5b2c9183bdc31601a86975da",
            "tags": [
                {
                    "_id": "5c2f3ab62abe843e6129fc4f",
                    "name": "Pragati Garg",
                    "email": "pragati@signzy.com",
                    "phone": "8787878787",
                    "tagType": [
                        "Authorised Signatory",
                        "Director"
                    ],
                    "merchantId": "5c2f3a942abe843e6129fc4e",
                    "documents": {
                        "5c2f3ab62abe843e6129fc4f1546599122541": {
                            "documentId": "5c2f3ab62abe843e6129fc4f1546599122541",
                            "docType": "idCard",
                            "docSubType": "individualPan",
                            "name": "panforme"
                        },
                        "5c2f3ab62abe843e6129fc4f1546605794047": {
                            "documentId": "5c2f3ab62abe843e6129fc4f1546605794047",
                            "docType": "idCard",
                            "docSubType": "individualPan",
                            "name": "panforme"
                        }
                    }
                }
            ]
        }
```

| Property | Accepted values/format | Description                                                                                          |
| -------- | ---------------------- | ---------------------------------------------------------------------------------------------------- |
| result   | Object                 | Merchant Object with all input data and array of all requestIds generated for the specified Merchant |
