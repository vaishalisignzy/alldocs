# Integration Document - Deprecated

## Introduction

Signzy ID Card Extraction SDK offers extraction of fields for various id cards even when the device is offline. The advantage of using this SDK is that the merchant app doesn't  need to specify the type of Id card being scanned for extraction. The SDK automatically detects the type of card and extracts the data.

This SDK provides two functionalities:

1. Classification of ID cards.
2. Extraction of ID cards.

## Integration

### Requirements

* Rear-facing camera
* **minSdkVersion** SDK version 21 (Android 5.0) or greater

### Setup

Add the **.aar** file provided by Signzy to the libs folder of your Android Project. Now you have to make it accessible so that it can be used in your project. There are two ways you can make it accessible:

1. In your **app level** **build.gradle** file you can add one more extension to **include** parameter dependencies section as shown below:

**Before:**

{% code title="build.gradle" %}
```groovy
dependencies {

    implementation fileTree(dir: 'libs', include: ['*.jar'])
    
    //...
}
```
{% endcode %}

**After:**

{% code title="build.gradle" %}
```groovy
dependencies {

    implementation fileTree(dir: 'libs', include: ['*.jar', '*.aar'])
    
    //...
}
```
{% endcode %}

&#x20;2\. You can also add the below line to make the **.aar** file accessible to your code. Add the below line of code in your **app level build.gradle** file:

{% code title="build.gradle" %}
```groovy
dependencies {

    implementation project(':signzy-sdk')
    // signzy-sdk is the name of the .aar file I have added in my libs
    // folder. 
    
    //...
}
```
{% endcode %}

Now add below dependencies in app level **build.gradle** file: &#x20;

{% code title="build.gradle" %}
```groovy
dependencies {
    //...

    implementation 'com.airbnb.android:lottie:$lottieVersion'
    implementation 'com.google.code.gson:gson:2.8.5'
    implementation 'com.google.android.material:material:1.0.0'
    //...
}
```
{% endcode %}

The SDK uses firebase dependencies so your project must be connected to Firebase and must contain **google-services.json** file:

```groovy
implementation 'com.google.firebase:firebase-ml-vision:latest-version'
```

### Usage

To open the SDK, use the below code snippet:

```java
 Intent intent = Intent(this, IntroSliderActivity.class); 
 intent.putExtra(IntroSliderActivity.SIGNZY_API_KEY, your_api_key);
 startActivityForResult(intent, REQUEST_CODE);
```

**your\_api\_key** will be provided by Signzy. The API key cannot be null otherwise the SDK won't open.

Override **onActivityResult** method to get the results once the extraction is complete as shown below:

```java
@Override
protected void onActivityResult(int requestCode, int resultCode, @Nullable Intent data) {
    super.onActivityResult(requestCode, resultCode, data);
        if (requestCode == REQUEST_CODE) {
            if (data != null && data.getExtras() != null) {
                ExtractionDetails details = 
                    data.getExtras().getParcelable(IntroSliderActivity.EXTRACTED_DETAILS);
                //....
        }
    }
}

```

To get the extracted attributes:

```java
if (details != null) {
      HashMap<Integer/*Page Number*/, HashMap<String/*Key*/, String/*Value*/>> extractedAttributes = details.getExtractionResults();
      HashMap<Integer/*Page Number*/, Bitmap/*Bitmap Image*/> bitmaps = details.getPageBitmaps();
      ArrayList<String> errorCodes = details.getErrorCodes();
      boolean isCardValid = details.isCardValid();
      boolean isExtractionValid = details.isExtractionValid();
}

```

**details.getExtractionResults()** gives all the extracted fields.

**details.getPageBitmaps()** gives all the bitmaps of extracted images.

**details.getErrorCodes()** gives a list of error codes. For example if the tokens are not available then the error code is **NO\_TOKENS.**                                                    &#x20;

**details.isCardValid()** gives the card state whether it is valid or invalid.&#x20;

**details.isExtractionValid()** is **true** if all the fields are extracted, **false** otherwise.

If you want autoRenew functionality, then you can use the following line of code:

```java
IntroSliderActivity.autoRenewTokens(int renewTokenThreshold, Context context, String apiKey);
```

For example, if **renewTokenThreshold** is set to 10 then when the tokens count reduces to 10 it will automatically renew tokens.

You can push tokens back to the server by using below line of code:

```java
IntroSliderActivity.pushBackTokensToServer(Context context, String apiKey);
```

To generate an API token, use the post request:

```java
//POST
https://xxx.signzy.tech/mobile/extraction/generatePermanentToken/

{
  "username":"your_user_name",
  "password":"your_password",
  "tokenChunk":"number_of_tokens"
}

```

**tokenChunk** is the number of tokens you want to issue. You will get the same number of tokens for every new install of SDK or for every new renewal of tokens.

The response will be similar to:

```java
{
    "status": "200",
    "contents": {
        "accessToken": "3EVqVmZyo2DjGDM1WzCscl600oiuIT9Lg93Dgww0mEUXkY3EBsSmKYYZLeLxJuhb",
        "userId": "5a905eda237c1a694a4119d8",
        "permanentToken": "AQX4Y8AHTJN4NUNVOABDVTOUCNJV9DV03N860Q47NM4RP5FCCP"
    }
}
```

**permanentToken** will be your API key while using this SDK.
