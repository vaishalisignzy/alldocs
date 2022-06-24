---
description: This document helps in integrating id-card-extraction module which does OCR
---

# Addition of the SDK to your project

## Requirements

**Developer Requirements**

The following tools should be installed:

* ****[**Android Studio**](https://developer.android.com/studio/)****
* ****[**JDK**](https://www.oracle.com/java/technologies/downloads/)****
* ****[**Android Project uses AndroidX**](https://developer.android.com/jetpack/androidx)****

{% hint style="info" %}
The Minimum API Level required is 21 (Android 5.0 and above)
{% endhint %}

**Device Requirements**

* A Device with a rear camera

**Permissions Required**

* Camera

## Setup

**Step 1:** Add the following code in project-level _build gradle_ file:

```
repositories {
        google()
        mavenCentral()
        maven {
            url "s3://maven.signzy"
            credentials(AwsCredentials) {
                accessKey "<<ACCESS_KEY>>"
                secretKey "<<SECRET_KEY>>"
            }
        }
    }
```

Here **accessKey** and **secretKey** will be provided by **Signzy.**

Should have build gradle version at least 3.4.0+.

**Step 2:** Add the following dependency in the app-level _build gradle_ file:

```
android {
    compileOptions {
        sourceCompatibility = '1.8'
        targetCompatibility = '1.8'
    }
}

dependencies {
    implementation("com.signzy:id_card_extraction:$VERSION") {
        transitive(true)
    }
}
```

Here _**VERSION**_ code can be found with respective [release notes](releases.md).

{% hint style="info" %}
It may require you to update kotlin version If you are using older one
{% endhint %}

## Sample Application

Download this zip file [https://drive.google.com/file/d/1YBiuzGurP6SeQ\_Csy1XMCY6aJvDg5c2T/view?usp=sharing](https://drive.google.com/file/d/1YBiuzGurP6SeQ\_Csy1XMCY6aJvDg5c2T/view?usp=sharing)

To make this sample application run you need to add Signzy API Key in MainActivity.kt file. And in Settings Gradle file add the access key and secret key provided by Signzy.

Also in app-level Build Gradle file define the appropriate version of this SDK
