# Combined OCR

## Extraction of Identity card

Before going for Auto reading or Verification calls, you first need to create an Identity object. To get an overview of the ID verification process visit here .For best results, please make sure that the image you use fits tightly in camera view and is horizontally-aligned. Each image/pdf should be less than 2MB and expired image should not be uploaded.

The Identity Card reading system accepts direct URL to the front and back sides.&#x20;

{% swagger baseUrl="https://preproduction.signzy.tech" path="/api/v2/snoops" method="post" summary="Identity Card Extraction" %}
{% swagger-description %}
**Production URL:**

\




`https://signzy.tech/api/v2/snoops`

\




\


This method allows data extraction from Indian OVDs. Please refer to the section "Aadhaar Card Extraction" and the tab "Response Parameter Aadhaar" for detailed explanation of output of Combined OCR API.
{% endswagger-description %}

{% swagger-parameter in="body" name="essentials,summary" type="string" %}
This parameter needs to be set to true to get the combined OCR response in output
{% endswagger-parameter %}

{% swagger-parameter in="body" name="essentials" type="string" %}
Contains essential input data
{% endswagger-parameter %}

{% swagger-parameter in="body" name="accessToken" type="string" %}
Contains the identity access token.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="task" type="string" %}
The task to be performed - Auto Recognition
{% endswagger-parameter %}

{% swagger-parameter in="body" name="itemId" type="string" %}
Contains the identity item id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="service " type="string" %}
Classifies the type of service - Identity
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
	"service": "Identity",
	"itemId": "<Identity-object-id>",
	"task": "autoRecognition",
	"essentials": {
                "summary" : "true"
        },
	"accessToken": "<Identity-access-token>",
	"id": "ID-of-the-snoop-request",
	"response": {
		"files": [
			"image-urls"
		],
		"type": "individualPan | businessPan",
		"id": ...integer...,
		"instance": {},
		"result": {
			"summary": {
      "number": "ID card number",
      "name": "Name of the ID holder",
      "dob": "Date of Birth of ID holder",
      "address": "Address of the ID holder",
      "splitAddress": {
				"district": [
					"..district.."
				],
				"state": [
					[
						"..state.."
					]
				],
				"city": [
					"..city.."
				],
				"pincode": "..pincode..",
				"country": [
					"IN",
					"IND",
					"INDIA"
				],
				"addressLine": "..addressLine.."
			},
			"gender" : "Gender of the ID holder",
			"guardianName": "Guardian/Father's name of ID holder",
			"issueDate": "Date of Issue of Id card",
			"expiryDate": "Date of Expiry of Id card",
			"placeOfBirth": "Place Of Birth",
			"placeOfIssue": "Place Of Issue",
			"bankName": "Name of the Bank",
			"micrCode": "MICR Code",
			"ifscCode": "IFSC Code"
    },
			"...result of ID Card Extractions. The response of each has been defined below..."
		}
	}
}
```
{% endswagger-response %}
{% endswagger %}

### Aadhaar Card Extraction

{% tabs %}
{% tab title="Request Schema" %}
```
{
        "service":"Identity",
        "itemId":"<Identity-id>",
        "task":"autoRecognition",
        "accessToken":"<Identity-access-token>",
        "essentials":{
                "summary" : "true"
        }
}
```
{% endtab %}

{% tab title="Response Schema Aadhaar" %}
```
 {
 	service: 'Identity',
 	itemId: '...id....',
 	task: 'autoRecognition',
 	essentials: {
                "summary" : "true"
        },
 	accessToken: '...access token from identity request...',
 	id: '...id...',
 	response: {
 		"files": [
 			"...image url..."
 		],
 		"id": ..xx..,
 		"instance": {},
 		"result": {
      "summary": {
      "number": "ID card number",
      "name": "Name of the ID holder",
      "dob": "Date of Birth of ID holder",
      "address": "Address of the ID holder",
      "splitAddress": {
				"district": [
					"..district.."
				],
				"state": [
					[
						"..state.."
					]
				],
				"city": [
					"..city.."
				],
				"pincode": "..pincode..",
				"country": [
					"IN",
					"IND",
					"INDIA"
				],
				"addressLine": "..addressLine.."
			},
			"gender" : "Gender of the ID holder",
			"guardianName": "Guardian/Father's name of ID holder",
			"issueDate": "Date of Issue of Id card",
			"expiryDate": "Date of Expiry of Id card",
			"placeOfBirth": "Place Of Birth",
			"placeOfIssue": "Place Of Issue",
			"bankName": "Name of the Bank",
			"micrCode": "MICR Code",
			"ifscCode": "IFSC Code"
    },
 			"uid": "...00000000XXXX....masked first eight digit...",
 			"vid": "...virtual UID...",
 			"name": "...name on id card...",
 			"yob": "...year of birth...",
 			"dob": "...date of birth...",
 			"pincode": "...pincode...",
 			"address": "...address as on card...",
 			"gender": "male/female",
 			"splitAddress": {
 				"district": [],
 				"state": [
 					[]
 				],
 				"city": [],
 				"pincode": " ",
 				"country": [
 					"IN",
 					"IND",
 					"INDIA"
 				],
 				"addressLine": ""
 			},
 			"uidHash": "Secure Cryptographic conversion of UID"
 		}
 	}
 }
```
{% endtab %}

{% tab title="Response Parameter Aadhaar" %}
| **PARAMETER  NAME**                     | DATA LENGTH | DATA TYPE       | **DESCRIPTION**                                                                                                                                                                                                                                         |
| --------------------------------------- | ----------- | --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| result.summary.ifscCode                 | 11          | String          | Contains IFSC code as on cheque                                                                                                                                                                                                                         |
| result.summary.micrCode                 | 9           | String          | Contains MICR code as on cheque                                                                                                                                                                                                                         |
| result.summary.bankName                 | 100         | String          | Contains the name of bank as on Cancelled cheque                                                                                                                                                                                                        |
| result.summary.placeOfIssue             | 200         | String          | Contains the place of issue of ID card                                                                                                                                                                                                                  |
| result.summary.placeOfBirth             | 200         | String          | Contains place of birth of card holder                                                                                                                                                                                                                  |
| result.summary.expiryDate               | 10          | String          | Contains the expiry date as on ID card. Format (dd/mm/yyyy)                                                                                                                                                                                             |
| result.summary.issueDate                | 10          | String          | Contains the issue date as on ID card. Format (dd/mm/yyyy)                                                                                                                                                                                              |
| result.summary.guardianName             | 100         | String          | Contains the guardian name of card holder                                                                                                                                                                                                               |
| result.summary.gender                   | 10          | String          | Contains the gender of the card holder                                                                                                                                                                                                                  |
| result.summary.splitAddress.addressLine | 1000        | String          | Contains the address obtained by removing extra spaces, hypens, slashes etc.                                                                                                                                                                            |
| result.summary.splitAddress.country     | 100         | Array           | Contains the country based on address on ID                                                                                                                                                                                                             |
| result.summary.splitAddress.pincode     | 6           | String          | Contains the pincode based on address on ID                                                                                                                                                                                                             |
| result.summary.splitAddress.city        | 100         | Array of String | Contains the city based on address on ID                                                                                                                                                                                                                |
| result.summary.splitAddress.state       | 100         | Array of Array  | Contains the state based on address on ID                                                                                                                                                                                                               |
| result.summary.splitAddress.district    | 100         | Array of String | Contains the district based on address on ID                                                                                                                                                                                                            |
| result.summary.splitAddress             |             | Object          | This parameter distinguishes the various parts of the address of the ID holder into separate categories like district, state, city, pincode and country                                                                                                 |
| result.summary.address                  | 1000        | String          | Address of the card holder                                                                                                                                                                                                                              |
| result.summary.dob                      | 10          | String          | Date of Birth of card holder. Format. Format (dd//mm/yyyy)                                                                                                                                                                                              |
| result.summary.name                     | 100         | String          | Name of the card holder                                                                                                                                                                                                                                 |
| result.summary.number                   | 100         | String          | ID Card Number                                                                                                                                                                                                                                          |
| result.summary                          |             | Object          | Contains the response of the Combined OCR                                                                                                                                                                                                               |
| service                                 | 10          | String          | Type of Signzy service - “identity extraction”                                                                                                                                                                                                          |
| itemId                                  | 30          | String          | Contains the identity item id                                                                                                                                                                                                                           |
| task                                    | 20          | String          | The type of task performed - “Auto Recognition”                                                                                                                                                                                                         |
| essentials                              |             | Object          | Contains the essential output data                                                                                                                                                                                                                      |
| accessToken&#xD;                        | 30          | String          | Contains the access token that was received from identity request&#xD;                                                                                                                                                                                  |
| Id                                      | 30          | String          | Contains the unique Id of the snoop request&#xD;                                                                                                                                                                                                        |
| response                                |             | Object          | Contains the output files                                                                                                                                                                                                                               |
| files                                   | 200         | Array of String | Contains the image URL of the output                                                                                                                                                                                                                    |
| result                                  |             | Object          | This parameter holds the final result parameters of the response.                                                                                                                                                                                       |
| result.uid&#xD;                         | 20          | String          | The unique Aadhaar ID number                                                                                                                                                                                                                            |
| result.vid&#xD;                         | 20          | String          | The Virtual Aadhaar ID number                                                                                                                                                                                                                           |
| result.name&#xD;                        | 100         | Stri            | This parameter contains the name on the ID card                                                                                                                                                                                                         |
| result.yob&#xD;                         | 10          | String          | This parameter returns the Year of birth of the ID holder&#xD;. Format (dd/mm/yyyy)                                                                                                                                                                     |
| result.dob&#xD;                         | 10          | String          | Date of birth of the ID holder. Format (dd/mm/yyyy)                                                                                                                                                                                                     |
| result.pincode                          | 6           | String          | The pincode of the ID card holder’s address&#xD;                                                                                                                                                                                                        |
| result.address                          | 200         | String          | The address of the ID card holder                                                                                                                                                                                                                       |
| result.gender&#xD;                      | 10          | String          | The gender of the ID card holder                                                                                                                                                                                                                        |
| result.splitAddress                     |             | Object          | This parameter distinguishes the various parts of the address of the ID holder into separate categories like district, state, city, pincode and country. For the country category, acceptable values (for Indian ID cards) is “IN”,”IND”and”INDIA”&#xD; |
| uidHash&#xD;                            | 100         | String          | Contains the encrypted hash value of the UID                                                                                                                                                                                                            |
{% endtab %}
{% endtabs %}

### PAN Card Extraction

{% tabs %}
{% tab title="Request Schema" %}
```
{
    "service":"Identity",
    "itemId":"<Identity-object-id>",
    "task":"autoRecognition",
    "accessToken":"<Identity-access-token>",
    "essentials":{
                "summary" : "true"
        }
}
```
{% endtab %}

{% tab title="Response Schema PAN" %}
```
{
	"service": "Identity",
	"itemId": "<Identity-object-id>",
	"task": "autoRecognition",
	"essentials": {
                "summary" : "true"
        },
	"accessToken": "<Identity-access-token>",
	"id": "ID-of-the-snoop-request",
	"response": {
		"files": [
			"<url-to-the-front-side>"
		],
		"type": "individualPan | businessPan",
		"id": ...integer...,
		"instance": {},
		"result": {
		  "summary": {
      "number": "ID card number",
      "name": "Name of the ID holder",
      "dob": "Date of Birth of ID holder",
      "address": "Address of the ID holder",
      "splitAddress": {
				"district": [
					"..district.."
				],
				"state": [
					[
						"..state.."
					]
				],
				"city": [
					"..city.."
				],
				"pincode": "..pincode..",
				"country": [
					"IN",
					"IND",
					"INDIA"
				],
				"addressLine": "..addressLine.."
			},
			"gender" : "Gender of the ID holder",
			"guardianName": "Guardian/Father's name of ID holder",
			"issueDate": "Date of Issue of Id card",
			"expiryDate": "Date of Expiry of Id card",
			"placeOfBirth": "Place Of Birth",
			"placeOfIssue": "Place Of Issue",
			"bankName": "Name of the Bank",
			"micrCode": "MICR Code",
			"ifscCode": "IFSC Code"
    },
			"name": "Name as on card | organization name in case of businessPan",
			"fatherName": "Father's name as on card, in case of individualPan only",
			"dob": "DOB as on card | dateOfIssue in case of businessPan",
			"number": "number as on card"
		}
	}
}
```
{% endtab %}

{% tab title="Response parameters PAN" %}
| **PARAMETER  NAME**                  | **DESCRIPTION**                                                     |
| ------------------------------------ | ------------------------------------------------------------------- |
| Service                              | Type of service - “identity”                                        |
| ItemId                               | Contains the identity item id                                       |
| Task                                 | The type of task performed - “Auto Recognition”                     |
| Essentials                           | Contains the essential output data                                  |
| <p>essentials.</p><p>accessToken</p> | Contains the access token that was received from identity request   |
| Essentials.id                        | Contains the unique Id of the snoop request                         |
| Response                             | Contains the output files                                           |
| Response.Files                       | Contains the image URL of the output.                               |
| type                                 | type of identity : "individualPAN/businessPAN"                      |
| id                                   | Unique id of the identity                                           |
| result                               | This holds final result parameters of the response.                 |
| result.name                          | Name of the PAN cardholder/Organisation name in case of businessPAN |
| result.fatherName                    | Father's name on the card (valid only for individual PAN)           |
| result.dob                           | Date Of Birth of cardholder/Date of Issue in case of businessPAN    |
| result.number                        | PAN number of the individual                                        |
{% endtab %}
{% endtabs %}

### Driving Licence Extraction

{% tabs %}
{% tab title="Request Schema" %}
```
{
    "service":"Identity",
    "itemId":"<Identity-id>",
    "task":"autoRecognition",
    "accessToken":"<Identity-access-token>",
    "essentials":{
                "summary" : "true"
        }
}
```
{% endtab %}

{% tab title="Response Schema Driving Licence" %}
```
{
	"service": "Identity",
	"itemId": "..item Id..",
	"task": "autoRecognition",
	"essentials": {
                "summary" : "true"
        },
	"accessToken": "...accessToken...",
	"id": "...id...",
	"response": {
		"files": ["...image url..."],
		"id": "ID-of-the-snoop-request",
		"instance": {
			"id": "...id...",
			"callbackUrl": "...callback url..."
		},
		"result": {
			"summary": {
      "number": "ID card number",
      "name": "Name of the ID holder",
      "dob": "Date of Birth of ID holder",
      "address": "Address of the ID holder",
      "splitAddress": {
				"district": [
					"..district.."
				],
				"state": [
					[
						"..state.."
					]
				],
				"city": [
					"..city.."
				],
				"pincode": "..pincode..",
				"country": [
					"IN",
					"IND",
					"INDIA"
				],
				"addressLine": "..addressLine.."
			},
			"gender" : "Gender of the ID holder",
			"guardianName": "Guardian/Father's name of ID holder",
			"issueDate": "Date of Issue of Id card",
			"expiryDate": "Date of Expiry of Id card",
			"placeOfBirth": "Place Of Birth",
			"placeOfIssue": "Place Of Issue",
			"bankName": "Name of the Bank",
			"micrCode": "MICR Code",
			"ifscCode": "IFSC Code"
    },
			"issueDate": "date-of-issue",
			"dob": "dob",
			"expiryDate": "date-of-expiry",
			"name": "name",
			"number": "dl number",
			"guardianName": "name of guardian",
			"address": "address",
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
			"dlType": ["array-of-vehicle-class"]
		}
	}
}
```
{% endtab %}

{% tab title="Response Parameters Driving Licence" %}
| **PARAMETER  NAME**    | **DESCRIPTION**                                                                                                                                                                                                                                    |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| service                | Type of Signzy service - “identity extraction”                                                                                                                                                                                                     |
| ItemId                 | Contains the identity item id                                                                                                                                                                                                                      |
| task                   | <p>The type of task performed - “Auto Recognition”<br></p>                                                                                                                                                                                         |
| essentials             | Contains the essential output data                                                                                                                                                                                                                 |
| essentials.accessToken | Contains the access token that was received from identity request&#xD;                                                                                                                                                                             |
| essentials.id&#xD;     | Contains the unique Id received from the identity request.&#xD;                                                                                                                                                                                    |
| response&#xD;          | Contains the output files&#xD;                                                                                                                                                                                                                     |
| response.files         | Contains the image URL of the output.&#xD;                                                                                                                                                                                                         |
| instance.callbackURL   | URL where the data is to be posted once the request is processed                                                                                                                                                                                   |
| result&#xD;            | This holds final result parameters of the response.&#xD;                                                                                                                                                                                           |
| result.issueDate       | This parameter contains the Date of Issue for the Driving Licence                                                                                                                                                                                  |
| result.dob&#xD;        | Date of birth of the DL holder                                                                                                                                                                                                                     |
| result.expiryDate      | expiry date of the driving licence                                                                                                                                                                                                                 |
| result.name            | The name on the driving licence.                                                                                                                                                                                                                   |
| result.number          | The driving licence number on the card                                                                                                                                                                                                             |
| result.guardianName    | The name of the individual's guardian as mentioned on the DL.                                                                                                                                                                                      |
| result.address         | Contains the address details under the parameter splitAddress.                                                                                                                                                                                     |
| address.splitAddress   | This parameter distinguishes the various parts of the address of the ID holder into separate categories like district, state, city, pincode and country. For the country category, acceptable values (for Indian ID cards) is “IN”,”IND”and”INDIA” |
| result.dlType          | The type of vehicle class for which DL has been assigned.                                                                                                                                                                                          |
{% endtab %}
{% endtabs %}

### Passport Extraction

{% tabs %}
{% tab title="Request Schema" %}
```
{
    "service":"Identity",
    "itemId":"<Identity-id>",
    "task":"autoRecognition","accessToken":"<Identity-access-token>",
    "essentials":{
                "summary" : "true"
        }
}
```
{% endtab %}

{% tab title="Response Parameters Passport" %}
```
{
	"service": "Identity",
	"itemId": "...item id...",
	"task": "autoRecognition",
	"essentials": {
                "summary" : "true"
        },
	"accessToken": "...access token...",
	"id": "..id...",
	"response": {
		"files": ["..image url..."],
		"id": "ID-of-the-snoop-request",
		"instance": {},
		"result": {
			"summary": {
      "number": "ID card number",
      "name": "Name of the ID holder",
      "dob": "Date of Birth of ID holder",
      "address": "Address of the ID holder",
      "splitAddress": {
				"district": [
					"..district.."
				],
				"state": [
					[
						"..state.."
					]
				],
				"city": [
					"..city.."
				],
				"pincode": "..pincode..",
				"country": [
					"IN",
					"IND",
					"INDIA"
				],
				"addressLine": "..addressLine.."
			},
			"gender" : "Gender of the ID holder",
			"guardianName": "Guardian/Father's name of ID holder",
			"issueDate": "Date of Issue of Id card",
			"expiryDate": "Date of Expiry of Id card",
			"placeOfBirth": "Place Of Birth",
			"placeOfIssue": "Place Of Issue",
			"bankName": "Name of the Bank",
			"micrCode": "MICR Code",
			"ifscCode": "IFSC Code"
    },
			"parentsGuardianName": "..parentsGuardianName...",
			"issueDate": "..issueDate..",
			"expiryDate": "..expiryDate..",
			"birthDate": "..birthDate..",
			"name": "..name..",
			"country": [
				"..country.."
			],
			"nationality": "..nationality..",
			"sex": "F/M",
			"address": "..address..",
			"pincode": "..pincode..",
			"passportNumber": "..passportNumber..",
			"fileNumber": "..fileNumber..",
			"placeOfBirth": "..placeOfBirth..",
			"placeOfIssue": "..placeOfIssue..",
			"splitAddress": {
				"district": [
					"..district.."
				],
				"state": [
					[
						"..state.."
					]
				],
				"city": [
					"..city.."
				],
				"pincode": "..pincode..",
				"country": [
					"IN",
					"IND",
					"INDIA"
				],
				"addressLine": "..addressLine.."
			}
		}
	}
}
```
{% endtab %}

{% tab title="Response Parameters Passport" %}


| **PARAMETER  NAME**         | **DESCRIPTION**                                                                                                                                                                                                                                    |
| --------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| service                     | Type of Signzy service - “identity extraction”                                                                                                                                                                                                     |
| itemId                      | Contains the identity item id                                                                                                                                                                                                                      |
| task                        | <p>The type of task performed - “Auto Recognition”<br></p>                                                                                                                                                                                         |
| essentials                  | Contains the essential output data                                                                                                                                                                                                                 |
| essentials.accessToken&#xD; | Contains the access token that was received from identity request&#xD;                                                                                                                                                                             |
| essentials.id&#xD;          | Contains the unique Id received from the identity request.                                                                                                                                                                                         |
| response                    | Contains the output files                                                                                                                                                                                                                          |
| response.files              | Contains the image URL of the output.&#xD;                                                                                                                                                                                                         |
| result                      | This holds the final result parameters of the response.&#xD;                                                                                                                                                                                       |
| result.parentsGuardianName  | The parent/guardian name as mentioned in the  passport.                                                                                                                                                                                            |
| result.dateofIssue          | This parameter returns the Date of Issue for the passport.                                                                                                                                                                                         |
| result.expiryDate           | Contains the Expiry date of the passport                                                                                                                                                                                                           |
| result.birthDate            | Holds the Date of birth of the passport holder                                                                                                                                                                                                     |
| result.name                 | Name of the passport holder                                                                                                                                                                                                                        |
| result.country              | This parameter returns the country information of the passport holder                                                                                                                                                                              |
| result.nationality          | This parameter returns the nationality details of the passport holder.                                                                                                                                                                             |
| result.sex                  | Contains two options: F for Female, M for Male. This is used to select the gender of the passport holder.                                                                                                                                          |
| result.address              | The address information of the passport holder                                                                                                                                                                                                     |
| result.pincode              | Contains the pincode for the above mentioned address                                                                                                                                                                                               |
| result.passportNumber       | This parameter returns the passport number for the uploaded passport                                                                                                                                                                               |
| result.fileNumber           | This parameter returns the passport file number for the uploaded passport                                                                                                                                                                          |
| result.placeofBirth         | Contains the place of birth details for the passport holder.                                                                                                                                                                                       |
| result.placeofIssue         | Contains the place of issue details for the passport holder.                                                                                                                                                                                       |
| result.splitAddress         | This parameter distinguishes the various parts of the address of the ID holder into separate categories like district, state, city, pincode and country. For the country category, acceptable values (for Indian ID cards) is “IN”,”IND”and”INDIA” |


{% endtab %}
{% endtabs %}

### Cheque Extraction

{% tabs %}
{% tab title="Request Schema" %}
```
{
    "service":"Identity",
    "itemId":"<Identity-id>",
    "task":"autoRecognition","accessToken":"<Identity-access-token>",
    "essentials":{
                "summary" : "true"
        }
}
```
{% endtab %}

{% tab title="Response Parameters Cheque" %}
```
{
	"service": "Identity",
	"itemId": "...item id...",
	"task": "autoRecognition",
	"essentials": {
                "summary" : "true"
        },
	"accessToken": "...access token...",
	"id": "..id...",
	"response": {
		"files": ["..image url..."],
		"id": "ID-of-the-snoop-request",
		"instance": {},
		"result": {
		  "summary": {
      "number": "ID card number",
      "name": "Name of the ID holder",
      "dob": "Date of Birth of ID holder",
      "address": "Address of the ID holder",
      "splitAddress": {
				"district": [
					"..district.."
				],
				"state": [
					[
						"..state.."
					]
				],
				"city": [
					"..city.."
				],
				"pincode": "..pincode..",
				"country": [
					"IN",
					"IND",
					"INDIA"
				],
				"addressLine": "..addressLine.."
			},
			"gender" : "Gender of the ID holder",
			"guardianName": "Guardian/Father's name of ID holder",
			"issueDate": "Date of Issue of Id card",
			"expiryDate": "Date of Expiry of Id card",
			"placeOfBirth": "Place Of Birth",
			"placeOfIssue": "Place Of Issue",
			"bankName": "Name of the Bank",
			"micrCode": "MICR Code",
			"ifscCode": "IFSC Code"
    },
			"address": "...address...",
			"ifsc": "...ifsc...",
			"pincode": "...pincode...",
			"accountNumber": "...accountNumber...",
			"bankName": "...bankName...",
			"micrCode": "....micrCode...",
			"contact": "...contact..",
			"branch": "...branch...",
			"name": "...name...",
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
			}
		}
	}
}
```
{% endtab %}

{% tab title="Response Parameters Cheque" %}
| PARAMETER NAME       | DESCRIPTION                                                                                                                                                                                                                            |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| result               | This holds the final response parameters.                                                                                                                                                                                              |
| result.address       | The address of the owner of the cancelled cheque.                                                                                                                                                                                      |
| result.ifsc          | The IFSC code of the bank to which the cancelled cheque is registered.                                                                                                                                                                 |
| result.pincode       | The pincode of the address which is registered to the cheque.                                                                                                                                                                          |
| result.accountNumber | The account number to which the cancelled cheque was issued.                                                                                                                                                                           |
| result.bankName      | The name of the bank which issued the cancelled cheque.                                                                                                                                                                                |
| result.micrCode      | The MICR code of the bank that issued the cheque.                                                                                                                                                                                      |
| result.contact       | The contact information of the bank which had issued the cheque.                                                                                                                                                                       |
| result.branch        | The branch of the bank that had issued the cancelled cheque.                                                                                                                                                                           |
| result.name          | The name of the individual on the cancelled cheque.                                                                                                                                                                                    |
| result.splitAddress  | This parameter distinguishes the various parts of the address of the cheque holder into separate categories like district, state, city, pincode and country. For the country category, acceptable values  is “IN”,”IND”and”INDIA”&#xD; |
| result.addressLine   | The first line of the address.                                                                                                                                                                                                         |
{% endtab %}
{% endtabs %}

