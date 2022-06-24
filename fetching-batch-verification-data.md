# Fetching Batch Verification Data

#### GET request <a href="#get-request" id="get-request"></a>

The token and id parameter in the URL below are obtained using the above API call.

```
// GET:: https://stripe-poc-prod.signzy.tech/api/patrons/:stripe-patron-id/registers/:register-id--received-from-register-call?token=:token--received-as-output-of-register-call

```

#### Expected response <a href="#expected-response_1" id="expected-response_1"></a>

```
{
    "data": [{
        "entity_type": "company",
        "stripe_merchant_id": "y97ai95byuuf5",
        "business_verifications": [{
            "input": {
                "type": "roc",
                "cin": "U74999PN2015PTC157118",
                "companyName": "SIGNZY TECHNOLOGIES PRIVATE LIMITED"
            },
            "result": {
                "verified": true,
                "message": "Verification completed with positive result"
            },
            "details": {
                "companyName": "SIGNZY TECHNOLOGIES PRIVATE LIMITED",
                "rocOffice": "RoC-Pune",
                "registrationNumber": "157118",
                "category": "Company limited by Shares",
                "subCategory": "Non-govt company",
                "class": "Private",
                "authorisedCapital": "1000000.0",
                "paidUpCapital": "123190.0",
                "numberOfMembers": "0",
                "dateOfIncorporation": "03/11/2015",
                "registeredAddress": "18 B, KUBERA BAHAR BUNGLOWS, SOC 131 2, BANER PASHAN LINK ROAD PUNE MH 411021 IN",
                "emailId": "arpitratan@gmail.com",
                "whetherListed": "Unlisted",
                "lastAgmDate": "31/12/2016",
                "balanceSheetDate": "31/03/2016",
                "statusForEfiling": "Active",
                "addressOtherThanRegisteredOffice": "",
                "suspendedAtStockExchange": "",
                "cin": "U74999PN2015PTC157118",
                "directorDetails": [{
                    "din": "06673269",
                    "designation": "Director",
                    "dateOfAppointment": "03/11/2015",
                    "address": "G-2, GANPATI ROYALE 30, SURYA NAGAR AGRA 282002 UP IN",
                    "dscExpiryDate": "10/09/2019",
                    "name": "ARPIT RATAN",
                    "whetherDscRegistered": "Yes",
                    "fatherName": "ALOKA KUMAR",
                    "dob": "08/03/1988",
                    "pan": "",
                    "splitAddress": {
                        "district": [
                            "AGRA"
                        ],
                        "state": [
                            [
                                "UTTAR PRADESH",
                                "UP"
                            ]
                        ],
                        "city": [
                            "AGRA"
                        ],
                        "pincode": "282002",
                        "country": [
                            "IN",
                            "IND",
                            "INDIA"
                        ],
                        "addressLine": "G-2,GANPATI ROYALE 30,SURYA NAGAR"
                    }
                }, {
                    "din": "06770480",
                    "designation": "Director",
                    "dateOfAppointment": "24/11/2016",
                    "address": "G-2, GANPATI ROYALE, 30 SURYA NAGAR, P.S. HARIPARVAT, AGRA 282002 UP IN",
                    "dscExpiryDate": "-",
                    "name": "ANKIT RATAN",
                    "whetherDscRegistered": "No",
                    "fatherName": "ALOKA KUMAR",
                    "dob": "08/03/1988",
                    "pan": "",
                    "splitAddress": {
                        "district": [
                            "AGRA"
                        ],
                        "state": [
                            [
                                "UTTAR PRADESH",
                                "UP"
                            ]
                        ],
                        "city": [
                            "AGRA"
                        ],
                        "pincode": "282002",
                        "country": [
                            "IN",
                            "IND",
                            "INDIA"
                        ],
                        "addressLine": "G-2,GANPATI ROYALE,30 SURYA NAGAR,P.S.HARIPARVAT"
                    }
                }],
                "pan": "",
                "splitAddress": {
                    "district": [
                        "PUNE"
                    ],
                    "state": [
                        [
                            "MAHARASHTRA",
                            "MH"
                        ]
                    ],
                    "city": [
                        "PUNE"
                    ],
                    "pincode": "411021",
                    "country": [
                        "IN",
                        "IND",
                        "INDIA"
                    ],
                    "addressLine": "18 B,KUBERA BAHAR BUNGLOWS,SOC 131 2,BANER PASHAN LINK ROAD"
                }
            }
        }, {
            "input": {
                "type": "gstin",
                "gstin": "19AAICP6253B1ZF",
                "companyName": "VIVEK  GUPTA"
            },
            "result": {
                "verified": false,
                "message": "Verification completed with negative result"
            },
            "details": {}
        }, {
            "input": {
                "type": "tan",
                "tan": "AGRA10865B",
                "companyName": "ALLAHABAD BANK"
            },
            "result": {
                "verified": true,
                "message": "Verification completed with positive result"
            },
            "details": {
                "verified": true,
                "message": "Verification completed with positive result"
            }
        }, {
            "input": {
                "type": "businessPan",
                "name": "SIGNZY TECHNOLOGIES PRIVATE LIMITEED",
                "number": "AAWCS3552Q"
            },
            "result": {
                "verified": false,
                "message": "Verification completed with negative result"
            },
            "details": {}
        }, {
            "input": {
                "type": "iec",
                "iec": "0903005891",
                "partyName": "BRAHMMAS AGRO INDUSTRIES PVT LTD"
            },
            "result": {
                "verified": false,
                "message": "Verification completed with negative result"
            },
            "details": {
                "iec": "0903005891",
                "iecAllotmentDate": "25/08/2003",
                "fileNumber": "09/04/130/00589/AM04/",
                "fileDate": "21/08/2003",
                "partyNameAndAddress": "PAAM COMMERCIAL PRIVATE LIMITED, NO.5-3-488,IST FLOOR, O.T.ROAD OSMANGUNJ HYDERABADA.P. PIN-500012",
                "partyName": "PAAM COMMERCIAL PRIVATE LIMITED",
                "partyAddress": "NO.5-3-488,IST FLOOR, O.T.ROAD OSMANGUNJ HYDERABADA.P. PIN-500012",
                "phone": "040 31033617",
                "email": "info@paamgroup.com",
                "exporterType": "4 Others",
                "dateOfEstablishment": "21/5/1998",
                "bin": "AADCA3323N",
                "natureOfConcern": "",
                "bankerDetail": "ING VYSYA BANK LTD,SIDDIAMBER BAZAR,HYDERABAD A/C Type:1 CA A/C No  :306011017503",
                "splitPartyAddress": {
                    "district": [
                        "HYDERABAD"
                    ],
                    "state": [
                        [
                            "TELANGANA",
                            "TG"
                        ]
                    ],
                    "city": [
                        "NAMPALLY"
                    ],
                    "pincode": "500012",
                    "country": [
                        "IN",
                        "IND",
                        "INDIA"
                    ],
                    "addressLine": "PAAM COMMERCIAL PRIVATE LIMITED,NO.5-3-488,IST FLOOR,O.T.ROAD OSMANGUNJ A.P"
                },
                "pan": "AADCA3323N",
                "branches": [],
                "directors": [{
                    "number": "1",
                    "address": "307, GARDEN MANOR,6.3.1097 & 1098 RAJ BHAVAN ROAD, HYDERABAD.AP PIN-500082 Phone/Email:",
                    "directorName": "SHRI ASHOK KUMAR AGARWAL",
                    "parentName": "SITARAM AGARWAL",
                    "splitAddress": {
                        "district": [
                            "HYDERABAD"
                        ],
                        "state": [
                            [
                                "TELANGANA",
                                "TG"
                            ]
                        ],
                        "city": [
                            "KHAIRATABAD"
                        ],
                        "pincode": "500082",
                        "country": [
                            "IN",
                            "IND",
                            "INDIA"
                        ],
                        "addressLine": "307,GARDEN MANOR,6.3.1097 1098 RAJ BHAVAN ROAD AP"
                    }
                }, {
                    "number": "2",
                    "address": "NO.307, GARDEN MANOR, NO.6-3-1097-98,RAJBHAWAN ROAD, SOMAJIGUDA,HYDERABAD AP PIN-500080 Phone/Email:9391033617",
                    "directorName": "SHRI POONAM DEVI AGARWAL",
                    "parentName": "SHRI ASHOK KUMAR AGARWAL",
                    "splitAddress": {
                        "district": [
                            "HYDERABAD"
                        ],
                        "state": [
                            [
                                "TELANGANA",
                                "TG"
                            ]
                        ],
                        "city": [
                            "SECUNDERABAD"
                        ],
                        "pincode": "500080",
                        "country": [
                            "IN",
                            "IND",
                            "INDIA"
                        ],
                        "addressLine": "NO.307,GARDEN MANOR,NO.6-3-1097-98,RAJBHAWAN ROAD,SOMAJIGUDA,AP"
                    }
                }]
            }
        }],
        "people_verifications": [{
            "input": {
                "type": "aadhaar",
                "uid": "XXXXXXXX7735",
                "name": "Apurba Kuiry",
                "dob": "XX/XX/1992"
            },
            "result": {
                "verified": false,
                "message": "Verification complete with negative results",
                "aadhaarMessage": "'Pi' (basic) attributes of demographic data did not match"
            },
            "details": {}
        }, {
            "input": {
                "type": "pan",
                "name": "Rahul Kumar",
                "number": "XXXXXXXXXX"
            },
            "result": {},
            "details": {}
        }],
        "beneficial_owners_verifications": [{
            "input": {
                "type": "beneficialOwnerVerification",
                "legalName": "Ankur Pandey",
                "percentageOwnership": "88"
            }
        }],
        "bank_account_verifications": [{
            "input": {
                "type": "bankAccountVerification",
                "accountNumber": "XXXXXXXXXX",
                "ifsc": "XXXXXXXXXX",
                "beneficiaryName": "Rahul Kumar"
            },
            "result": {
                "verified": true,
                "message": "Verification completed with positive result"
            },
            "details": {
                "actCode": "0",
                "response": "Transaction Successful",
                "bankRRN": "XXXXXXXXXx",
                "beneName": "RAHUL KUMAR",
                "tranRefNo": "XXXXXeShZsrmtY6SNe6KkY0zECjdajVMpbNxckps8VpnnKHx46",
                "paymentRef": "Account verification",
                "tranDateTime": "18-10-2017 17:16:47",
                "amount": "0.05",
                "beneMMID": "9013001",
                "beneMobile": "",
                "beneIFSC": "XXXXXXXXXX"
            }
        }],
        "signzyProcessorId": "XXXXXXXXjUvx4RuUf40oFA2HIZPkyyYaIb257JS4bjunZDVqLM4jZVIa1BMrja",
        "random": "random"
    }],
    "id": "59e73f28affe446698f5a047",
    "patronId": "59e46c68fa06992903b4a9c7",
    "token": "XXXXXXX"
}
```

