# KYC Registration Request

## KYC Registration request <a href="#kyc-registration-request" id="kyc-registration-request"></a>

The role of this endpoint is to register a batch KYC process for stripe’s merchants.

### API Request <a href="#api-request" id="api-request"></a>

https://stripe-poc-prod.signzy.tech/api/patrons/:stripe-patron-id/registers

**stripe-patron-id is the userId field returned in login request.**

**Supported entity\_type:** company, proprietorship, opc, llp, registeredPartnership, unregisteredPartnership

#### Sample input <a href="#sample-input" id="sample-input"></a>

A sample input to the register endpoint is as below.

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
      }
    }, {
      "input": {
        "type": "gstin",
        "gstin": "19AAICP6253B1ZF",
        "companyName": "VIVEK  GUPTA"
      }
    }, {
      "input": {
        "type": "tan",
        "tan": "AGRA10865B",
        "companyName": "ALLAHABAD BANK"
      }
    }, {
      "input": {
        "type": "businessPan",
        "name": "SIGNZY TECHNOLOGIES PRIVATE LIMITEED",
        "number": "AAWCS3552Q"
      }
    }, {
      "input": {
        "type": "iec",
        "iec": "0903005891",
        "partyName": "BRAHMMAS AGRO INDUSTRIES PVT LTD"
      }
    }],
    "people_verifications": [{
      "input": {
        "type": "aadhaar",
        "uid": "XXXXXXXXXXXX",
        "name": "Apurba Kuiry",
        "dob": "XX/XX/1992"
      }
    }, {
      "input": {
        "type": "pan",
        "name": "Rahul Kumar",
        "number": "DPNXXXX77N"
      }
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
        "accountNumber": "94521XXXX010870",
        "ifsc": "BKIXXXX9462",
        "beneficiaryName": "Rahul Kumar"
      }
    }]
  }]
}

```

#### Expected response <a href="#expected-response" id="expected-response"></a>

The response contains two important properties viz id and token. These both need to be provided in the fetch verification data call to fetch the batch KYC data.

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
            }
        }, {
            "input": {
                "type": "gstin",
                "gstin": "19AAICP6253B1ZF",
                "companyName": "VIVEK  GUPTA"
            }
        }, {
            "input": {
                "type": "tan",
                "tan": "AGRA10865B",
                "companyName": "ALLAHABAD BANK"
            }
        }, {
            "input": {
                "type": "businessPan",
                "name": "SIGNZY TECHNOLOGIES PRIVATE LIMITEED",
                "number": "AAWCS3552Q"
            }
        }, {
            "input": {
                "type": "iec",
                "iec": "0903005891",
                "partyName": "BRAHMMAS AGRO INDUSTRIES PVT LTD"
            }
        }],
        "people_verifications": [{
            "input": {
                "type": "aadhaar",
                "uid": "XXXXXXXX7735",
                "name": "Apurba Kuiry",
                "dob": "XX/XX/1992"
            }
        }, {
            "input": {
                "type": "pan",
                "name": "Rahul Kumar",
                "number": "XXXXXXXXXX"
            }
        }],
        "beneficial_owners_verifications": [],
        "bank_account_verifications": [{
            "input": {
                "type": "bankAccountVerification",
                "accountNumber": "XXXXXXXXXX",
                "ifsc": "XXXXXXXXXX",
                "beneficiaryName": "Rahul Kumar"
            }
        }],
        "signzyProcessorId": "BHhdMCdxUcWmPpwKwiOGJoqQ5CNXu9sjM2RSfmB8RfhEseH5mVhaFt1hw9WW",
        "random": "random"
    }],
    "id": "59e73127cfcda62cf9070bc6",
    "patronId": "59d8db66d5cdf3cc896fcb17",
    "token": "XXXXXXX"
}
```

