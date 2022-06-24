# Onboard a customer

Onboard a new customer to your card program with the “Register” API endpoint. The API contains the KYC fields where the customer can be registered using Paper KYC, E-KYC, or Biometric KYC. If Biometric KYC is invoked, you need to call our KYC API before calling this API. Upon successful verification of all other parameters, the API returns a success response in JSON. Each unique Customer is identified using the “entityId” variable which will be extensively used in all other APIs.

{% swagger method="post" path="/register" baseUrl="https://<< BASE URL>>/Yappay/registration-manager/v3" summary="" %}
{% swagger-description %}

{% endswagger-description %}
{% endswagger %}

#### Request Body

```
{
"entityId": "123453227",
"entityType": "CUSTOMER",
"businessType": "PRDEMO",
"otp": "123456",
"businessId": "+919524599398",
"countryofIssue": "IND",
"cardType": "P",
"kitNo": "900009908",
"title": "Mr",
"firstName": "PRDEMO",
"lastName": "CUSTOMER01",
"gender": "M",
"specialDate": "1999-09-29",
"contactNo": "+919524599398",
"emailAddress": "email@signzy.in",
"address": "my address, my street",
"address2": "my locality",
"city": "mycity",
"state": "mystate",
"country": "India",
"pincode": "600000",
"idType": "PAN",
"idNumber": "1234400101",
"idExpiry": "2020-12-12",
"eKycRefNo": "12345678",
"kycStatus": "FULL_KYC",
"countryCode": "12345",
"programType": " PRDEMO",
"documents": [
{
" docType ": "PAN",
" docNo ": "ADOPA89013",
"docExpDate": null
},
{
" docType ": "PASSPORT",
" docNo ": "ADOPA89013",
" docExpDate ": "2025-12-12"
}
],
"addressDto": {
"contactNo1": "+919677109523",
"contactNo2": "+919236634491",
"emailAddress1": "maddy@signzy.in",
"emailAddress2": "maddy.v@gmail.com",
"notification": "1010",
"address": [
{
"title": "PERMANENT,",
"address1": "chennai,",
"address2": "aalandur",
"address3": "airport",
"city": "Chennai",
"state": "TamilNadu",
"country": "India",
"pinCode": "600091"
}
]
}
}
```

#### Response Body

```
{
"entityId": "Same as the request's Entity Id"
}
```
