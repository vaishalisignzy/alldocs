# Combined Fetch

## Fetch API for Individual ID and Entity data

This API specifies the details for integrating the Fetch APIs for Individual OVDs and Entity data. The APIs covered here are as given below:

Individual OVDs:

1. PAN Fetch
2. Voter ID Fetch
3. Driving License Fetch
4. Indian Passport Fetch

Entity:

1. GSTIN Search
2. ROC/MCA - Company Simple Search by CIN
3. ROC/MCA - Simple Search by DIN
4. Udhyog Aadhaar - Search by UAN
5. SNEC
6. VAT&#x20;



{% swagger baseUrl="https://preproduction.signzy.tech/api" path="/v2/patrons/..your-patron-id../globaldatafetches" method="post" summary="Combined Fetch API" %}
{% swagger-description %}
Production URL:

\


https://signzy.tech/api/v2/patrons/<patron-id>/globaldatafetches
{% endswagger-description %}

{% swagger-parameter in="body" name="inputData.state" type="string" %}
State where the Individual OVD was made or entity registered. This parameter is mandatory only for Voter ID, and SNEC APIs
{% endswagger-parameter %}

{% swagger-parameter in="body" name="inputData.dob" type="string" %}
Date of Birth as given in Indian OVDs. This parameter is mandatory for DL and Passport, and not required for others
{% endswagger-parameter %}

{% swagger-parameter in="body" name="inputData.number" type="string" %}
The actual ID/Entity number to for whom data is to be fetched
{% endswagger-parameter %}

{% swagger-parameter in="body" name="inputData.type" type="string" %}
This parameter describes the actual API to be hit. Possible values are: "pan", "drivingLicense", "indianPassport", "voterId", "businessPan", "gstSearch", "simpleSearchCin", "simpleSearchDin", "tin" (for VAT API), "snec", "udhyogAadhaarUan"
{% endswagger-parameter %}

{% swagger-parameter in="body" name="patronId" type="string" %}
This is the "userId" value from the Login request
{% endswagger-parameter %}

{% swagger-parameter in="body" name="queryType" type="string" %}
This parameter describes whether the request is for Individual or Entity. Possible values: "individual", "entity"
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
For Invididuals
{
	"queryType": "individual"
	"summary": {
		"name": "Name",
		"number": "Number",
		"dob": "dob",
	},
	"detailed": {
		"...detailed API response as it is..."
	}
} 

For Entities
{
	"queryType": "entity"
	"summary": {
		"name": "",
		"number": "",
		"status": "",
		"registrationDate": "",
		"address": "",
		"splitAddress": ""
	},
	"detailed": {
		"...detailed API response as it is..."
	}
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="Request Schema " %}
```
{
    "essentials": {
			"queryType": "individual/entity",
		  "inputData": {
		     "type": "type of ID to be fetched",
		     "number": "Number of OVD/Entity",
		     "dob": "Date of Birth",
		     "state": "State"
	    }
    }
}
```
{% endtab %}

{% tab title="Response Parameter" %}
| Parameter Name                             | Data Type | Data Length | Description                                                               |
| ------------------------------------------ | --------- | ----------- | ------------------------------------------------------------------------- |
| summary.name                               | String    | 200         | Name                                                                      |
| summary.number                             | String    | 50          | Number                                                                    |
| summary.dob                                | String    | 10          | Date of Birth                                                             |
| summary.status                             | String    | 100         | Status of Entity (active, inactive etc)                                   |
| summary.address                            | String    | 1000        | Address of the Entity (This is not applicable for individuals)            |
| summary.registrationDate                   | String    | 10          | Registration date of entity (not for individuals)                         |
| detailed.directorDetails.din               | String    | 50          | DIN of director (only for MCA - Simple Search by CIN API)                 |
| detailed.directorDetails.name              | String    | 200         | Name of Director (only for MCA - Simple Search by CIN API)                |
| detailed.directorDetails.dateOfAppointment | String    | 10          | Date of Appointment of Director (only for MCA - Simple Search by CIN API) |


{% endtab %}
{% endtabs %}

## Responses for Individual OVDs

{% tabs %}
{% tab title="PAN Response" %}
```
{
	"queryType": "individual"
	"summary": {
		"name": "Name",
		"number": "Number",
		"dob": "dob",
	},
	"detailed": {
        "name": "..name..",
        "fatherName": "..fatherName..",
        "dob": "..dob..",
        "number": "..pan number.."
	}
} 
```
{% endtab %}

{% tab title="Voter ID Response" %}
```
{
	"queryType": "individual"
	"summary": {
		"name": "Name",
		"number": "Number",
		"dob": "dob",
	},
	"detailed": {
        "name": "....name...",
        "dob": "....dob....",
        "district": "...district...",
        "state": ".....state....",
        "fatherName": "....fathers name...",
        "gender": "....gender...."
	}
} 
```
{% endtab %}

{% tab title="DL Response" %}
```
{
	"queryType": "individual"
	"summary": {
		"name": "Name",
		"number": "Number",
		"dob": "dob",
	},
	"detailed": {
  		"dlNumber": "...dlNumber...",
        "dob": "...dob...",
  		"badgeDetails": [{
  			"badgeIssueDate": "...badgeDetails...",
  			"badgeNo": "...badgeNo...",
  			"classOfVehicle": "...classOfVehicle..."
  		}],
  		"dlValidity": {
  			"nonTransport": {
  				"to": "...to...",
  				"from": "...from..."
  			},
  			"hazardousValidTill": "...hazardousValidTill...",
  			"transport": {
  				"to": "...to...",
  				"from": "...from..."
  			},
  			"hillValidTill": "...hillValidTill..."
  		},
  		"detailsOfDrivingLicence": {
  			"dateOfIssue": "...dateOfIssue...",
  			"dateOfLastTransaction": "...dateOfLastTransaction...",
  			"status": "...status...",
  			"lastTransactedAt": "...lastTransactedAt...",
  			"name": "...name...",
  			"fatherOrHusbandName": "...fatherOrHusbandName...",
  			"address": "...address...",
        "addressList": [
         {
           "completeAddress": "...completeAddress...",
           "type": "...type...",
           "splitAddress": {
             "district": [],
             "state": [
               []
             ],
             "city": [],
             "pincode": "...pincode...",
             "country": [
               "IN",
               "IND",
               "INDIA"
             ],
             "addressLine": "...addressLine..."
           }
         }],
  			"photo": "...photo...",
  			"splitAddress": {
  				"state": [
  					[]
  				],
  				"district": [],
  				"city": [],
  				"pincode": "...pincode...",
  				"country": [
  					"IN",
  					"IND",
  					"INDIA"
  				],
  				"addressLine": "...addressLine..."
  			},
  			"covDetails": [{
  				"covCategory": "...covCategory...",
  				"classOfVehicle": "...classOfVehicle...",
  				"covIssuedate": "...covIssuedate..."
  			}]
  		}
  	}
} 
```
{% endtab %}

{% tab title="Indian Passport Response" %}
```
{
	"queryType": "individual"
	"summary": {
		"name": "Name",
		"number": "Number",
		"dob": "dob",
	},
	"detailed": {
        "fileNumber": "..fileNumber..",
        "givenName": "..givenName..",
        "surname": "..surname..",
        "typeOfApplication": "..typeOfApplication..",
        "applicationReceivedOnDate": "..applicationReceivedOnDate..",
        "name": "..name..",
        "dob": "..dob.."
	}
} 
```
{% endtab %}
{% endtabs %}

## Responses for Entities

{% tabs %}
{% tab title="GST Response" %}
```
{
	"queryType": "entity"
	"summary": {
		"name": "",
		"number": "",
		"status": "",
		"registrationDate": "",
		"address": ""
	},
	"detailed": {
  		"gstnRecords": [{
  				"regType": "..registrationType...",
  				"emailId": "..emailId...",
  				"applicationStatus": "...application Status...",
  				"registrationName": "...registered Name...",
  				"gstinRefId": "...GSTIN Reference Id...",
  				"tinNumber": "...Tin Number...",
  				"mobNum": "...Mobile Number...",
  				"gstin": "...gstin Number..."
  			}

  		],
  		"gstnDetailed": {
  			"constitutionOfBusiness": "....Constitution Of Business...",
  			"legalNameOfBusiness": "....Name Of Business...",
            "tradeNameOfBusiness": "....Trade Name Of Business...",
  			"centreJurisdiction": "....Centre Of Jurisdiction...",
  			"stateJurisdiction": "....State Of Jurisdiction...",
  			"registrationDate": "...Date of Registration...",
  			"taxPayerDate": "...Tax Payer Date...",
            "taxPayerType": "...Tax Payer Type...",
            "gstinStatus": "..GSTIN Status...",
  			"cancellationDate": "..cancellation Date...",
  			"natureOfBusinessActivities": [
  				"...Nature of Business Activities..."
  			],
  			"principalPlaceAddress": "...Principal Address of the entity registered in GST...",
            "principalPlaceLatitude": "...Principal Latitude of the entity registered in GST...",
            "principalPlaceLongitude": "...Principal Longitude of the entity registered in GST...",
            "principalPlaceBuildingNameFromGST": "...Bulding Name of Principal Address of the entity registered in GST...",
  			"principalPlaceBuildingNoFromGST": "...Bulding No of Principal Address of the entity registered in GST...",
  			"principalPlaceFlatNo": "...Flat No of Principal Address of the entity registered in GST...",
            "principalPlaceStreet": "...Street of Principal Address of the entity registered in GST...",
            "principalPlaceLocality": "...Locality of Principal Address of the entity registered in GST...",
            "principalPlaceCity":"...City of Principal Address of the entity registered in GST...",
            "principalPlaceDistrict":"...District of Principal Address of the entity registered in GST...",
            "principalPlaceState":"...State of Principal Address of the entity registered in GST...",
            "principalPlacePincode":"...Pincode of Principal Address of the entity registered in GST...",
  			"additionalPlaceAddress": "...Additional Address of the entity registered in GST...",
            "additionalPlaceLatitude": "...Additional Latitude of the entity registered in GST...",
            "additionalPlaceLongitude": "...Additional Longitude of the entity registered in GST...",
            "additionalPlaceBuildingNameFromGST": "...Bulding Name of Additional Address of the entity registered in GST...",
            "additionalPlaceBuildingNoFromGST": "...Bulding No of Additional Address of the entity registered in GST...",
  			"additionalPlaceFlatNo": "...Flat No of Additional Address of the entity registered in GST...",
            "additionalPlaceStreet": "...Street of Additional Address of the entity registered in GST...",
            "additionalPlaceLocality": "...Locality of Additional Address of the entity registered in GST...",
            "additionalPlaceCity":"...City of Additional Address of the entity registered in GST...",
            "additionalPlaceDistrict":"...District of Additional Address of the entity registered in GST...",
            "additionalPlaceState":"...State of Additional Address of the entity registered in GST...",
            "additionalPlacePincode":"...Pincode of Additional Address of the entity registered in GST...",
  			"principalPlaceSplitAddress": {
  				"state": [
  					[]
  				],
  				"district": [],
  				"city": [],
  				"pincode": "...pincode...",
  				"country": [
  					"IN",
  					"IND",
  					"INDIA"
  				],
  				"addressLine": "...addressLine..."
  			},
  			"additionalPlaceSplitAddress": {
  				"state": [
  					[]
  				],
  				"district": [],
  				"city": [],
  				"pincode": "...pincode...",
  				"country": [
  					"IN",
  					"IND",
  					"INDIA"
  				],
  				"addressLine": "...addressLine..."
  			}
  		},
  		"gstin": "...gstin Number..."
  	}
}
```
{% endtab %}

{% tab title="MCA Simple Search by CIN Response" %}
```
{
	"queryType": "entity"
	"summary": {
		"name": "",
		"number": "",
		"status": "",
		"registrationDate": "",
		"address": ""
	},
	"detailed": {
    "companyName": "...companyName...",
    "rocOffice": "...rocOffice...",
    "registrationNumber": "...registrationNumber...",
    "category": "...category...",
    "subCategory": "...subCategory...",
    "class": "...class...",
    "authorisedCapital": "...authorisedCapital...",
    "paidUpCapital": "...paidUpCapital...",
    "numberOfMembers": "...numberOfMembers...",
    "dateOfIncorporation": "...dateOfIncorporation...",
    "registeredAddress": "...registeredAddress...",
    "pan": "...pan...",
    "emailId": "...emailId...",
    "whetherListed": "...whetherListed...",
    "lastAgmDate": "...lastAgmDate...",
    "balanceSheetDate": "...balanceSheetDate...",
    "status": "...status...",
    "addressOtherThanRegisteredOffice": "...addressOtherThanRegisteredOffice...",
    "suspendedAtStockExchange": "...suspendedAtStockExchange...",
    "natureOfBusiness": "...natureOfBusiness...",
    "splitAddress": {
      "state": [
        [

        ]
      ],
      "district": [

      ],
      "city": [],
      "pincode": "...pincode...",
      "country": [
        "IN",
        "IND",
        "INDIA"
      ],
      "addressLine": "...addressLine..."
    },
    "cin": "...cin...",
    "directorDetails": [
      {
        "name": "...name...",
        "fatherName": "...fatherName...",
        "dob": "...dob...",
        "pan": "...pan...",
        "din": "...din...",
        "dscExpiryDate": "...dscExpiryDate...",
        "dateOfAppointment": "...dateOfAppointment...",
        "designation": "...designation...",
        "address": "...address...",
        "splitAddress": {
          "state": [
            [

            ]
          ],
          "district": [

          ],
          "city": [],
          "pincode": "...pincode...",
          "country": [
            "IN",
            "IND",
            "INDIA"
          ],
          "addressLine": "...addressLine..."
        },
        "whetherDscRegistered": "...whetherDscRegistered..."
      }
    ]
  }
}
```
{% endtab %}

{% tab title="MCA Simple Search by DIN Response" %}
```
{
	"queryType": "entity"
	"summary": {
		"name": "",
		"number": "",
		"status": "",
		"registrationDate": "",
		"address": ""
	},
	"detailed": {
    "din": "..din..",
    "designation": "..designation..",
    "address": "..address..",
    "name": "..name..",
    "dob": "..dob..",
    "noOfCompanies": "..noOfCompanies..",
    "splitAddress": {
      "state": [
        [

        ]
      ],
      "district": [

      ],
      "city": [],
      "pincode": "...pincode...",
      "country": [
        "IN",
        "IND",
        "INDIA"
      ],
      "addressLine": "...addressLine..."
  },
  "listOfCompanies": [{
      "cinin": "..cinin..",
      "companyName": "..companyName..",
      "beginDate": "..beginDate..",
      "endDate": "..endDate..."
  }],
  "listOfLLPs": [{
        "llpin": "..llpin..",
        "llpName": "..llpName..",
        "beginDate": "..beginDate..",
        "endDate": "..endDate..."
    }]
  }
}
```
{% endtab %}

{% tab title="Udhyog Aadhaar UAN" %}
```
{
	"queryType": "entity"
	"summary": {
		"name": "",
		"number": "",
		"status": "",
		"registrationDate": "",
		"address": ""
	},
	"detailed": {
       "nameofEnterprise": "...nameofEnterprise...",
       "dateofCommencement": "...dateofCommencement...",
       "state": "...state...",
       "dicName": "...dicName...",
       "status": "...status..."
   }
}
```
{% endtab %}

{% tab title="VAT Response" %}
```
{
	"queryType": "entity"
	"summary": {
		"name": "",
		"number": "",
		"status": "",
		"registrationDate": "",
		"address": ""
	},
	"detailed": [
            {
                "cstStatus": "",
                "pan": "",
                "status": "",
                "ownerName": "",
                "dealer": "",
                "address": "",
                "regDate": "",
                "cancelDate": "",
                "splitAddress": {
                    "district": [],
                    "state": [
                        []
                    ],
                    "city": [],
                    "pincode": "",
                    "country": [
                        "IN",
                        "IND",
                        "INDIA"
                    ],
                    "addressLine": ""
                }
            }
        ]
}
```
{% endtab %}

{% tab title="SNEC Response" %}
```
Response for West Bengal State
{
	"queryType": "entity"
	"summary": {
		"name": "",
		"number": "",
		"status": "",
		"registrationDate": "",
		"address": ""
	},
	"detailed": {
	          "name": "",
            "dateOfCommencement": "",
            "address": "",
            "splitAddress": {
                "district": [""],
                "state": [
                    [
                        "WEST BENGAL",
                        "WB"
                    ]
                ],
                "city": [""],
                "pincode": "",
                "country": [
                    "IN",
                    "IND",
                    "INDIA"
                ],
                "addressLine": ""
      }
	}
}


Response for Telangana State
{
	"queryType": "entity"
	"summary": {
		"name": "",
		"number": "",
		"status": "",
		"registrationDate": "",
		"address": ""
	},
	"detailed": {   
  "name": "",
  "dateOfCommencement": "",
  "splitAddress": {
    "district": [],
    "state": [
      []
    ],
    "city": [],
    "pincode": "",
    "country": [
      "IN",
      "IND",
      "INDIA"
    ],
    "addressLine": ""
  }
	}
}

Response for Delhi State
{
	"queryType": "entity"
	"summary": {
		"name": "",
		"number": "",
		"status": "",
		"registrationDate": "",
		"address": ""
	},
	"detailed": {
      "name": "",
      "dateOfCommencement": "",
      "address": "",
      "splitAddress": {
        "district": [
          ""
        ],
        "state": [
          [
            "DELHI",
            "DL"
          ]
        ],
        "city": [
          "DELHI"
        ],
        "pincode": "",
        "country": [
          "IN",
          "IND",
          "INDIA"
        ],
        "addressLine": ""
      }
	}
}

Response for Haryana state
{
	"queryType": "entity"
	"summary": {
		"name": "",
		"number": "",
		"status": "",
		"registrationDate": "",
		"address": ""
	},
	"detailed": {
        "name": "",
        "dateOfCommencement": "",
        "address": "",
        "splitAddress": {
          "district": [
            ""
          ],
          "state": [
            [
              "HARYANA",
              "HR"
            ]
          ],
          "city": [
            ""
          ],
          "pincode": "",
          "country": [
            "IN",
            "IND",
            "INDIA"
          ],
          "addressLine": ""
        }
	}
}

Response for Rajasthan state
{
	"queryType": "entity"
	"summary": {
		"name": "",
		"number": "",
		"status": "",
		"registrationDate": "",
		"address": ""
	},
	"detailed": {
	    "name": "",
      "dateOfCommencement": "",
      "address": "",
      "splitAddress": {
        "district": [],
        "state": [
          []
        ],
        "city": [],
        "pincode": "",
        "country": [],
        "addressLine": ""
      }
	}
}


Response for Uttar Pradesh state
{
	"queryType": "entity"
	"summary": {
		"name": "",
		"number": "",
		"status": "",
		"registrationDate": "",
		"address": ""
	},
	"detailed": {
            "name": "...name...",
             "dateOfCommencement": "...dateOfCommencement...",
             "address": "...address...",
             "splitAddress":  {
                  "state": [
                    []
                  ],
                  "district": [],
                  "city": [],
                  "pincode": "...pincode...",
                  "country": [
                    "IN",
                    "IND",
                    "INDIA"
                  ],
                  "addressLine": "...addressLine..."
    }
	}
}
```
{% endtab %}
{% endtabs %}
