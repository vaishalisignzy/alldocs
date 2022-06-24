# Getting results to callback

This section explains how the callback system receives the submitted data once the video conference is concluded.

**A Callback URL need to be specified in the "Create Call API".**&#x20;

Once the call is concluded **** between the RE & the end user, the entire data gets automatically posted to the specified Callback URL with the customer details & the unique session ID. &#x20;

## Expected response to the Callback after successful completion

{% tabs %}
{% tab title="Callback Data" %}
```javascript
{
	"data": {
		"documents": [{
			"image": "image URL",
			"data": {
				"dob": "date of birth",
				"name": "name of user"
			}
		}],
		"_id": "5e45000e4f023c741c76bca9",
		"name": "name of user",
		"email": "emailof@user.com",
		"instructions": [{
			"isIDCardBoxRequired": true,
			"isSideNavRequired": true,
			"isScreenshotRequired": true,
			"text": "Please Show your PAN Card",
			"translations": {
				"ENGLISH": "Please Show your PAN Card",
				"HINDI": "कृपया अपना पैन कार्ड दिखाएं",
				"KANNADA": "ದಯವಿಟ್ಟು ನಿಮ್ಮ ಪ್ಯಾನ್ ಕಾರ್ಡ್ ತೋರಿಸುವುದೇ?",
				"BENGALI": "দয়া করে আপনার প্যান কার্ডটি দেখান?",
				"GUJARATI": "કૃપા કરીને તમારું પાન કાર્ડ બતાવો?"
			}
		}, {
			"isIDCardBoxRequired": false,
			"isSideNavRequired": false,
			"isScreenshotRequired": false,
			"text": "What is your Name?",
			"translations": {
				"ENGLISH": "What is your Name?",
				"HINDI": "तुम्हारा नाम क्या हे?",
				"KANNADA": "ನಿನ್ನ ಹೆಸರೇನು?",
				"BENGALI": "আপনার নাম কি?",
				"GUJARATI": "તમારું નામ શું છે?"
			}
		}, {
			"isIDCardBoxRequired": false,
			"isSideNavRequired": true,
			"isScreenshotRequired": false,
			"text": "What is your DOB?",
			"translations": {
				"ENGLISH": "What is your Date of Birth?",
				"HINDI": "आपका Date of Birth क्या है?",
				"KANNADA": "ನಿಮ್ಮ Date of Birth ಎಂದರೇನು?",
				"BENGALI": "আপনার ডিওবি কি?",
				"GUJARATI": "તમારું ડીઓબી શું છે?"
			}
		}],
		"randomizeInstructions": false,
		"recordingId": "Sgqho2lvHrpnY2p23cSCyrTn9A6wKtGARVtv9WjmqCksBpNMfVx7LhWT3oPonAEYBA5atS",
		"feedback": "4.5",
		"feedbackMessage": "good",
		"screenshots": [{
			"finalImage": "..screenshot taken during call URL..",
			"screenshots": [
				"..screenshots taken during call URL.."
			]
		}, {
			"finalImage": "",
			"screenshots": [

			]
		}, {
			"finalImage": "",
			"screenshots": [

			]
		}],
		"geo": {
			"statusCode": "OK",
			"statusMessage": "",
			"ipAddress": "..ip address..",
			"countryCode": "IN",
			"countryName": "India",
			"regionName": "Maharashtra",
			"cityName": "Mumbai",
			"zipCode": "400099",
			"latitude": "..lat..",
			"longitude": "..long..",
			"timeZone": "+05:30",
			"ip": "..ip address..",
			"city": "Mumbai"
		},
		"browserData": {
			"browserName": "Chrome",
			"cookieEnabled": "true",
			"browserLanguage": "en-IN",
			"os": "Win32",
			"userAgent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3987.100 Safari/537.36",
			"pluginsInstalled": [
				"Chrome PDF Plugin",
				"Chrome PDF Viewer",
				"Native Client"
			],
			"browserVersion": "Chrome 80",
			"screenWidth": "1920",
			"screenHeight": "1080",
			"screenPixelDepth": "24",
			"screenColorDepth": "24",
			"deviceInfo": {
				"complete_device_name": "Google Chrome",
				"form_factor": "Desktop",
				"is_mobile": false
			}
		},
		"forensicsData": {
			"ipQuality": {
				"isSet": 0
			}
		},
		"fieldValues": {
			"Remark": "Accepted",
			"ItemsToSelect": [
				"Internet Slow",
				"Recheck Required"
			]
		},
		"recordedVideoData": {
			"videoThumbnail": "..URL of video thumbnail..",
			"videoUrl": "..URL of video.."
		},
		"sessionId": "..unique session id.."
	},
	"callbackParameters": {
		"id": "parameters for callback data"
	}
}
```
{% endtab %}
{% endtabs %}

### Description of the parameters in Callback

| Property             | Data Type        | Description                                     |
| -------------------- | ---------------- | ----------------------------------------------- |
| data                 | Object           | video conference session Info                   |
| -- documents         | Array of Objects | List of user documents                          |
| -- \_id              | String           | Record Id                                       |
| --  sessionId        | String           | Unique Identifier for Video session             |
| -- instructions      | Array of objects | Sequence of instructions as shown to user       |
| -- recordedVideoData | Object           | Contains URLs of recorded video                 |
| ---- videoThumbnail  | URL String       | Image thumbnail from recorded video             |
| ---- videoUrl        | URL String       | Recorded Video URL                              |
| -- feedback          | String           | Conference experience rating by `VCIP Admin`    |
| -- feedbackMessage   | String           | Feedback by `Presenter`                         |
| callbackParameters   | Object           | As given by client in `createCall` request Body |
