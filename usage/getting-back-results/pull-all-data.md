---
description: >-
  After successful onboarding, we can fetch the merchants' details. We can get
  the list of merchants which is created based on the criteria provided in the
  API request.
---

# Pull All Data

{% swagger baseUrl="https://go-preproduction.signzy.app" path="/api/merchants/data" method="post" summary="Get All Data" %}
{% swagger-description %}
This method gives data of all the merchants
{% endswagger-description %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
access-token returned from the backops login

\


request
{% endswagger-parameter %}

{% swagger-parameter in="body" name="signzyAppIds" type="array" %}
array of numbers to filter result by signzyAppId
{% endswagger-parameter %}

{% swagger-parameter in="body" name="applicationId" type="string" %}
applicationId returned from backops login request
{% endswagger-parameter %}

{% swagger-parameter in="body" name="status" type="string" %}
status of the merchants (accept|reject|pending|all)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="skip" type="number" %}
records you want to skip
{% endswagger-parameter %}

{% swagger-parameter in="body" name="limit" type="number" %}
limit the number of records
{% endswagger-parameter %}

{% swagger-response status="200" description="Data successfully retrieved." %}
```
{
    "result": [{
        "result": {
            "merchantData": {
                "basicDetails": {
                    "name": "..name..",
                    "username": "..username..",
                    "email": "..email..",
                    "mobile": "..mobile..",
                    "realm": "..realm..",
                    "status": "..status..",
                    "autoLoginUrl": "..autoLoginUrl..",
                    "flowDetails": "..flowDetails..",
                    "applicationId": "..applicationId..",
                    "reason": "..reason..",
                    "instructions": "..instructions..",
                    "backopsFormData": "..backopsFormData..",
                    "backopsUserId": "..backopsUserId..",
                    "onboardingStartDate": "..onboardingStartDate..",
                    "onboardingEndDate": "..onboardingEndDate..",
                    "subStatus": "..subStatus.."
                },
                "documents": [{
                    "variable1": "...variable1...",
                    "variable2": "...variable2...",
                    "variable3": "...variable3...",
                    "variable4": "...variable4...",
                    "variable5": "...variable5...",
                    "variable6": "...variable6...",
                    "variable7": "...variable7...",
                    "type": "..type..",
                    "widgetName": "..widgetName.."
                }],
                "formData": {
                    "variable8": "...variable8...",
                    "variable9": "...variable9...",
                    "variable10": "...variable10...",
                    "variable11": "...variable11...",
                    "variable12": "...variable12...",
                    "variable13": "...variable13..."
                },
                "videoForensics": {
                    "audioMatchScore": "..audioMatchScore..",
                    "videoMatchScore": "..videoMatchScore..",
                    "videoCoVariance": "..videoCoVariance..",
                    "videoFinalImage": "..videoFinalImage..",
                    "videoUrl": "..videoUrl..",
                    "videoOtp": "..videoOtp..",
                    "videoFaceLandmark": "..videoFaceLandmark..",
                    "videoPrerecordedRisk": "..videoPrerecordedRisk..",
                    "videoStaticRisk": "..videoStaticRisk..",
                    "videoLandMark": "..videoLandMark..",
                    "image1": "..image1..",
                    "image2": "..image2..",
                    "image3": "..image3.."
                },
                "contract": {},
                "products": [],
                "browserAndLocationInfo": {
                    "browserInfo": {
                        "browserName": "..browserName..",
                        "fullVersion": "..fullVersion..",
                        "majorVersion": "..majorVersion..",
                        "cookiesEnabled": "..cookiesEnabled..",
                        "browserLanguage": "..browserLanguage.."
                    },
                    "locationInfo": {
                        "ip": "..ip..",
                        "city": "..city..",
                        "region": "..region..",
                        "region_code": "..region_code..",
                        "country": "..country..",
                        "country_code": "..country_code..",
                        "country_code_iso3": "..country_code_iso3..",
                        "country_capital": "..country_capital..",
                        "country_tld": "..country_tld..",
                        "country_name": "..country_name..",
                        "continent_code": "..continent_code..",
                        "in_eu": "..in_eu..",
                        "postal": "..postal..",
                        "latitude": "..latitude..",
                        "longitude": "..longitude..",
                        "timezone": "..timezone..",
                        "utc_offset": "..utc_offset..",
                        "country_calling_code": "..country_calling_code..",
                        "currency": "..currency..",
                        "currency_name": "..currency_name..",
                        "languages": "..languages..",
                        "country_area": "..country_area..",
                        "country_population": "..country_population..",
                        "asn": "..asn..",
                        "org": "..org.."
                    }
                },
                "appAndLocationInfo": "..appAndLocationInfo..",
                "matcherData": [{
                    "data": [{
                            "variable": "..variable..",
                            "value": "..value.."
                        },
                        {
                            "variable": "..variable..",
                            "value": "..value.."
                        }
                    ],
                    "matchScore": "..matchScore.."
                }]
            }
        }
    }]
}
```
{% endswagger-response %}

{% swagger-response status="400" description="For invalid parameters" %}
```
{
    "error": {
        "statusCode": 400,
        "name": "Error",
        "message": "Not a valid status"
    }
}
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
{% endswagger %}

### Sample request-response and field description

{% tabs %}
{% tab title="Sample Request Body" %}
```
{
    "applicationId": "..applicationId..",
    "status": "..status..",
    "limit": "..limit..",
    "skip": "..skip..",
    "signzyAppIds" : [..signzyAppId..]
}
```

#### Request Field Description

| Key           | Type                           | Description                                                   |
| ------------- | ------------------------------ | ------------------------------------------------------------- |
| applicationId | string                         | applicationId returned from the backops user login            |
| status        | string                         | status of the merchants (accept\|reject\|pending\|all)        |
| limit         | number                         | limit the number of records in response                       |
| skip          | number                         | records you want to skip from 0th document                    |
| signzyAppIds  | <p>array of </p><p>numbers</p> | fetch data of specific signzyAppIds for ex : \[100000000586]  |
{% endtab %}
{% endtabs %}
