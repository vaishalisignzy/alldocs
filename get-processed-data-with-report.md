---
description: >-
  Call this endpoint to get processed data and report after 5-10 mins of
  submitting the previous decision engine request.
---

# Get Processed data with report

{% swagger baseUrl="https://{domain-name}/api/getDEReport/:reqId" path="" method="get" summary="Get processed data" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
Authentication token to track down who is emptying our stocks.
{% endswagger-parameter %}

{% swagger-response status="200" description="Data successfully retrieved." %}
```
{
    "result": {
    "reportUrl": "...reportUrl...",
    "finalResult": {
        "result": "true"
    },
    "pageResults": {
        "5f1927e8e5063219c689c64c": [
                {
                    "textMatchData": {
                        "GSTINConstitutionOfBusinessMatchScore": "...score...",
                        "GSTINLegalNameOfBusinessMatchScore": "...score...",
                        "GSTINTradeNameOfBusinessMatchScore": "...score...",
                        "GSTINCentreJurisdictionMatchScore": "...score...",
                        "GSTINStateJurisdictionMatchScore": "...score...",
                        "GSTINRegistrationDateMatchScore": "...score...",
                        "GSTINTaxPayerDateMatchScore": "...score...",
                        "GSTINTaxPayerTypeMatchScore": "...score...",
                        "GSTINGstinStatusMatchScore": "...score...",
                        "GSTINCancellationDateMatchScore": "...score...",
                        "GSTINPrincipalPlaceAddressMatchScore": "...score...",
                        "GSTINPrincipalPlaceLatitudeMatchScore": "...score...",
                        "GSTINPrincipalPlaceLongitudeMatchScore": "...score...",
                        "GSTINAdditionalPlaceAddressMatchScore": "...score...",
                        "GSTINAdditionalPlaceLatitudeMatchScore": "...score...",
                        "GSTINAdditionalPlaceLongitudeMatchScore": "...score...",
                        "textMatchVariables": [
                            "GSTINGstImage",
                            "GSTINConstitutionOfBusiness",
                            "GSTINLegalNameOfBusiness",
                            "GSTINTradeNameOfBusiness",
                            "GSTINCentreJurisdiction",
                            "GSTINStateJurisdiction",
                            "GSTINRegistrationDate",
                            "GSTINTaxPayerDate",
                            "GSTINTaxPayerType",
                            "GSTINGstinStatus",
                            "GSTINCancellationDate",
                            "GSTINPrincipalPlaceAddress",
                            "GSTINPrincipalPlaceLatitude",
                            "GSTINPrincipalPlaceLongitude",
                            "GSTINAdditionalPlaceAddress",
                            "GSTINAdditionalPlaceLatitude",
                            "GSTINAdditionalPlaceLongitude"
                        ],
                        "type": "textmatch"
                    }
                }
            ],
            "5f1926415286ec19c0ad893b": [
                {
                    "addressMatchData": {
                        "matchScore": "10",
                        "address1-address2": 10,
                        "addressMatchVariables": [
                            "DrivingLicenseAddress",
                            "DrivingLicenseAddress_OCR"
                        ],
                        "type": "addressMatch"
                    },
                    "dateMatchData": {
                        "matchScore": "10",
                        "date1-date2": 10,
                        "dateMatchVariables": [
                            "DrivingLicenseDob",
                            "DrivingLicenseDob_OCR"
                        ],
                        "type": "dateMatch"
                    },
                    "nameMatchData": {
                        "matchScore": "10",
                        "name1-name2": 10,
                        "nameMatchVariables": [
                            "DrivingLicenseName",
                            "DrivingLicenseName_OCR"
                        ],
                        "type": "nameMatch"
                    },
                    "textMatchData": {
                        "nameMatchScore": 1,
                        "dobMatchScore": 1,
                        "DrivingLicenseIssueDateMatchScore": 1,
                        "DrivingLicenseExpiryDateMatchScore": 1,
                        "DrivingLicenseNumberMatchScore": 1,
                        "DrivingLicenseGuardianNameMatchScore": 1,
                        "DrivingLicenseAddressMatchScore": "1.00",
                        "DrivingLicenseDLTypeMatchScore": 0.4,
                        "textMatchVariables": [
                            "DrivingLicenseImage1",
                            "DrivingLicenseImage2",
                            "DrivingLicenseName",
                            "DrivingLicenseDob",
                            "DrivingLicenseIssueDate",
                            "DrivingLicenseExpiryDate",
                            "DrivingLicenseNumber",
                            "DrivingLicenseGuardianName",
                            "DrivingLicenseAddress",
                            "DrivingLicenseDLType"
                        ],
                        "type": "textmatch"
                    }
                }
            ],
            "5f19251c5286ec19c0ad893a": [
                {
                    "addressMatchData": {
                        "matchScore": "10",
                        "address1-address2": 10,
                        "addressMatchVariables": [
                            "VoterIdAddress",
                            "VoterIdAddress_OCR"
                        ],
                        "type": "addressMatch"
                    },
                    "dateMatchData": {
                        "matchScore": "10",
                        "date1-date2": 10,
                        "dateMatchVariables": [
                            "VoterIdDob",
                            "VoterIdDob_OCR"
                        ],
                        "type": "dateMatch"
                    },
                    "nameMatchData": {
                        "matchScore": "10",
                        "name1-name2": 10,
                        "nameMatchVariables": [
                            "VoterIdName",
                            "VoterIdName_OCR"
                        ],
                        "type": "nameMatch"
                    },
                    "textMatchData": {
                        "nameMatchScore": 1,
                        "dobMatchScore": 1,
                        "VoterIdEpicNumberMatchScore": 1,
                        "VoterIdFatherNameMatchScore": 1,
                        "VoterIdYobMatchScore": 1,
                        "VoterIdAddressMatchScore": "0.90",
                        "VoterIdStateMatchScore": 0.44,
                        "textMatchVariables": [
                            "VoterIdImage1",
                            "VoterIdImage2",
                            "VoterIdName",
                            "VoterIdDob",
                            "VoterIdEpicNumber",
                            "VoterIdFatherName",
                            "VoterIdYob",
                            "VoterIdAgeAsOn",
                            "VoterIdAddress",
                            "VoterIdState"
                        ],
                        "type": "textmatch"
                    }
                }
            ],
            "5f1922b5e5063219c689c64b": [
                {
                    "nameMatchData": {
                        "matchScore": "10",
                        "name1-name2": 10,
                        "nameMatchVariables": [
                            "AadhaarName",
                            "AadhaarName_OCR"
                        ],
                        "type": "nameMatch"
                    },
                    "addressMatchData": {
                        "matchScore": "10",
                        "address1-address2": 10,
                        "addressMatchVariables": [
                            "AadhaarAddress",
                            "AadhaarAddress_OCR"
                        ],
                        "type": "addressMatch"
                    },
                    "dateMatchData": {
                        "matchScore": "10",
                        "date1-date2": 10,
                        "dateMatchVariables": [
                            "AadhaarDob",
                            "AadhaarDob_OCR"
                        ],
                        "type": "dateMatch"
                    },
                    "textMatchData": {
                        "nameMatchScore": 1,
                        "dobMatchScore": 1,
                        "AadhaarUidMatchScore": 0.42,
                        "AadhaarVidMatchScore": 0,
                        "AadhaarYobMatchScore": 1,
                        "AadhaarPincodeMatchScore": 1,
                        "AadhaarAddressMatchScore": "1.00",
                        "AadhaarGenderMatchScore": 0.75,
                        "textMatchVariables": [
                            "AadhaarImage1",
                            "AadhaarImage2",
                            "AadhaarName",
                            "AadhaarDob",
                            "AadhaarUid",
                            "AadhaarVid",
                            "AadhaarYob",
                            "AadhaarPincode",
                            "AadhaarAddress",
                            "AadhaarGender"
                        ],
                        "type": "textmatch"
                    }
                }
            ],
            "5f1920ede5063219c689c64a": [
                {
                    "dateMatchData": {
                        "matchScore": "10",
                        "date1-date2": 10,
                        "dateMatchVariables": [
                            "IndividualPanDateOfBirth",
                            "IndividualPanDateOfBirth_OCR"
                        ],
                        "type": "dateMatch"
                    },
                    "nameMatchData": {
                        "matchScore": "10",
                        "name1-name2": 10,
                        "nameMatchVariables": [
                            "IndividualPanName",
                            "IndividualPanName_OCR"
                        ],
                        "type": "nameMatch"
                    },
                    "textMatchData": {
                        "nameMatchScore": 1,
                        "dobMatchScore": 1,
                        "IndividualPanFatherNameMatchScore": 1,
                        "IndividualPanPanNumberMatchScore": 1,
                        "textMatchVariables": [
                            "IndividualPanImage",
                            "IndividualPanName",
                            "IndividualPanDateOfBirth",
                            "IndividualPanFatherName",
                            "IndividualPanPanNumber"
                        ],
                        "type": "textmatch"
                    }
                }
            ]
        }
    } 
}
```
{% endswagger-response %}

{% swagger-response status="204" description="" %}
```
{"message": "Your request is under process. Please try after sometime "}
```
{% endswagger-response %}

{% swagger-response status="401" description="" %}
```
{
    "error": {
        "statusCode": 401,
        "name": "Error",
        "message": "Authorization Required",
        "code": "AUTHORIZATION_REQUIRED"
    }
}
```
{% endswagger-response %}

{% swagger-response status="404" description="" %}
```
{}
```
{% endswagger-response %}
{% endswagger %}

