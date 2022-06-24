# Know Investor's KYC Status

To comply with the PMLA guidelines, KYC (Know Your Customer) of an investor is an important and first step to begin the investment Journey.&#x20;

Mutuals funds in India are regulated by SEBI (Securities and Exchange Board of India) and it mandates all the financial intermediaries to follow certain guidelines in establishing and verifying the identity of an investor before accepting any investments from them, which is commonly called as KYC (Know your customer).

You can check the KYC status of the investor using the below API endpoint. If an investor has not completed the KYC, in such scenarios, you can use Signzy's Investor Onboarding Solution to complete the KYC of the investor and push the KYC data to the KRA (KYC Registration Agency).

## Know Investor's KYC Status

{% swagger method="get" path="/" baseUrl="https://<<BASE URL>>/know_investor_kyc_status" summary="Get to know the KYC status of an Investor." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="pan_number" type="String" required="true" %}
PAN number of the Investor
{% endswagger-parameter %}

{% swagger-parameter in="body" name="date_of_birth" type="String" required="true" %}
Date of birth of the Investor
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "name": "",
    "kycStatus": "",
    "gender": "",
    "dateOfBirth": "",
    "fatherName": "",
    "maritalStatus": "",
    "citizenship": "",
    "residentiaStatus": "",
    "correspondenceAddress": {
        "addressOne": "",
        "addressTwo": "",
        "city": "",
        "pincode": "",
        "state": "",
        "country": ""
    },
    "permanentAddress": {
        "addressOne": "",
        "addressTwo": "",
        "city": "",
        "pincode": "",
        "state": "",
        "country": ""
    },
    "email": "",
    "mobile": ""
}
```
{% endswagger-response %}
{% endswagger %}
