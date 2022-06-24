# Pull Data By Id

After successful onboarding, we can fetch the details of a particular merchant using the id which is created by create request. Keep a time gap of 2-3 minutes before pulling the merchant's data.

{% swagger baseUrl="https://go-preproduction.signzy.app" path="/api/merchants/:merchantId/data" method="get" summary="Get Data by Id" %}
{% swagger-description %}
This method gives the data about a particular merchant
{% endswagger-description %}

{% swagger-parameter in="path" name="merchantId" type="string" %}
Unique identifier of the merchant returned from

\


create request
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" type="string" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authentication" type="string" %}
access-token returned from backops user login
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
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
}
```
{% endswagger-response %}

{% swagger-response status="401" description="Need to check access token" %}
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

### Sample response and field description

{% tabs %}
{% tab title="Sample Response Body" %}
```
{
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
}
```

#### Response Field Descriptions

| Key                    | Type             | Description                                               |
| ---------------------- | ---------------- | --------------------------------------------------------- |
| merchantData           | object           | This contains all the data of the merchant                |
| basicDetails           | object           | Contains basic details of the merchant and onboarding     |
| documents              | array of objects | Contains data about documents collected in the onboarding |
| formData               | object           | User entered data                                         |
| videoForensics         | object           | Data returned from video KYC and verification             |
| contract               | object           | Contains data of digital contract                         |
| products               | array of objects | Contains data of opted products                           |
| browserAndLocationInfo | object           | Contains data about merchants location and browser        |
| browserInfo            | object           | Contains browser info                                     |
| locationInfo           | object           | Contains location info based on ISP                       |
| matcherData            | array of objects | Contains data of name match/text match/address match      |
{% endtab %}
{% endtabs %}
