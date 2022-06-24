---
description: >-
  This module serve as a video-verification gesture recognition supported app
  solution, which is attached with permission handling and another required
  environment to run in android Web-view.
---

# Android Integration Document

## Introduction

Signzy Video gesture verification is a Face gesture recognition tool to check the liveliness of the video, This SDK serves as the module to integrate the video verification in the android mobile application.

## Integration

### Requirements

* front-facing camera.
* Permission for location, camera, microphone.
* **minSdkVersion** SDK version 19 (Android 3.0) or greater

### Setup

Your app must have below permissions to integrate this SDK.

```markup
    <uses-permission android:name="android.permission.CAMERA" />
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.RECORD_AUDIO" />
    <uses-permission android:name="android.permission.MODIFY_AUDIO_SETTINGS" />
    <uses-feature android:name="android.hardware.camera" />
    <uses-feature android:name="android.hardware.camera.autofocus" />
```

The SDK is purely written in Kotlin, so if your app is written in Java then you need to make the following changes.

Add the following code in **app level build.gradle file:**

{% code title="build.gradle(app level)" %}
```
android {

    //...
    //...
    
    compileOptions {
        sourceCompatibility JavaVersion.VERSION_1_8
        targetCompatibility JavaVersion.VERSION_1_8
    }
}
dependencies {
    //...
    implementation 'org.jetbrains.kotlin:kotlin-stdlib-jdk7:1.3.72'
    implementation 'androidx.core:core-ktx:1.3.1'
    implementation 'androidx.appcompat:appcompat:1.2.0'
    implementation 'androidx.constraintlayout:constraintlayout:2.0.1'

}
```
{% endcode %}

To open the SDK use the below code snippet:

#### Java:

{% code title="IntegratorActivity.java" %}
```java
SignzySDKParams sdkParms = new SignzySDKParams(toolbarRequired/*True or false if toolbar required*/,
                titleHeader/*Title to be placed in header*/,
                colorCode/*Six digit hex code for color of toolbar*/,
                stringUrl/*URL for video verification*/)
Intent intent = new Intent(this, WebVideoVerificationActivity.class);
intent.putExtra("SIGNZY_PARAMS",sdkParams);
startActivityForResult(intent, WebVideoVerificationActivity.REQUEST_CODE);
```
{% endcode %}

#### Kotlin:

{% code title="IntegratorActivity.kt" %}
```kotlin
val sdkParams = SignzySDKParams(toolbarRequired/*True or false if toolbar required*/,
                titleHeader/*Title to be placed in header*/,
                colorCode/*Six digit hex code for color of toolbar*/,
                stringUrl/*URL for video verification*/)
Intent(this,WebVideoVerificationActivity::class.java)
                .putExtra("SIGNZY_PARAMS",sdkParams)
                .also {
                startActivityForResult(it,WebVideoVerificationActivity.SIGNZY_REQUEST_CODE)
                           }
```
{% endcode %}

### Results:

You need to override the **onActivityResult** method to get the results:

#### Java:

```java
@Override
protected void onActivityResult(int requestCode, int resultCode, @Nullable Intent data) {
    if (requestCode == REQUEST_CODE) {
        if (resultCode == RESULT_OK) {
            //Sucessfully completed the Video Verification
            }
        }

        if (resultCode == RESULT_CANCELED) {
            if (data != null && data.getExtras() != null) {
                String error = data.getExtras().getString(WebVideoVerificationActivity.SIGNZY_ERROR);
                Log.d(TAG, "Error: " + error);
                Toast.makeText(this, error, Toast.LENGTH_LONG).show();
            }
        }
    }
    super.onActivityResult(requestCode, resultCode, data);
}
```

#### Kotlin:

```java
override fun onActivityResult(requestCode: Int, resultCode: Int, data: Intent?) {

    if (requestCode == CODE) {
        if (resultCode == Activity.RESULT_OK) {
            //Sucessfully completed VV-gesture
        }
        if (resultCode == Activity.RESULT_CANCELED) {
            data?.extras?.let {
                Log.d(TAG, "Error: ${it.getString(WebVideoVerificationActivity.SIGNZY_ERROR)}")
                Toast.makeText(
                    this,
                    "${it.getString(WebVideoVerificationActivity.SIGNZY_ERROR)}",
                    Toast.LENGTH_LONG
                ).show()
            }
        }
    }
    super.onActivityResult(requestCode, resultCode, data)
}
```







