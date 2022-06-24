---
description: All the data points neeed for a KYC application
---

# Required information about the investor

#### Data points <a href="#data-points" id="data-points"></a>

The following information about the investor needs to be collected for a successful kyc submission

1. Full name of the investor (`name`)
2. PAN number of the investor (`pan`)
3. Email ID and mobile number of the investor (`email`, `mobile`)
4. Date of birth (`date_of_birth`)
5. Last 4 digits of the Aadhaar number (`aadhaar_number`)
6. Father name or spouse name in full (`father_name`, `spouse_name`)
7. Mother name in full (`mother_name`)
8. Gender (`gender`)
9. Country of birth (`country_of_birth`)
10. Marital status (`marital_status`)
11. Residential status (currently we only support indian resident individual) (`residential_status`)
12. Occupation (`occupation_type`)
13. Address with proof (`address`)
14. PAN card copy (`identity_proof`)
15. Signature scan (`signature`)
16. Photo (`photo`)
17. Verification video (`ipv_video`)
18. Bank account details with proof (`bank_account`)
19. Geo location (`geolocation`)
20. Fatca/CRS self declaration (TBD)
21. Electronic signature on the application form

\*TBD: We will provide the field names when the APIs are released

#### Accepted address proofs <a href="#accepted-address-proofs" id="accepted-address-proofs"></a>

The following address proofs are accepted currently. We will include more in the future.

| Address proof         | Data required                                                                                                                |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| Passport              | <p>1. Passport number<br>2. Front page and back page scan of the passport<br>3. Passport issue date and expiry date</p>      |
| Driving licence       | <p>1. Driving licence number<br>2. Front page and back page scan of the licence<br>3. Licence issue date and expiry date</p> |
| Voter's identity card | <p>1. ID card number<br>2. Front page and back page scan of the ID</p>                                                       |

#### Accepted bank account proofs <a href="#accepted-bank-account-proofs" id="accepted-bank-account-proofs"></a>

The following bank account proofs are accepted currently.

| Bank account proof | Notes                                                                                                  |
| ------------------ | ------------------------------------------------------------------------------------------------------ |
| Cancelled cheque   | Front scan of the cancelled cheque containing account number, name of the account holder and IFSC code |
| Passbook statement | Front page scan of the passbook which contains name of the account holder and account number           |

#### In person verification video <a href="#in-person-verification-video" id="in-person-verification-video"></a>

The verification video

* should be atleast 10 seconds long to be able to clearly detect the face of the person
* should have the investor reading the 6 digit OTP or he/she displaying the OTP written on a piece of paper

We have made some sample videos for your reference:

Insert Videos:

1. Investor reading the 6 digit OTP loud
2. Investor displaying the 6 digit OTP
3. Esign on the application form - web and mobile

\
