# Offline Aadhaar XML extraction

## Introduction

Offline-Aadhaar is an Android SDK that can be used to download the .zip file of Aadhaar Card from the UIDAI official website.&#x20;

Latest release version name - 1.0.3.

## Integration

Your app must have **minSdkVersion** set to **21** and must have the below permissions to integrate this SDK.

```markup
<uses-permission android:name="android.permission.INTERNET" />
```

The SDK is purely written in Kotlin.

Add the following code in **project level build.gradle file:**

```
// Some code
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

Add the following code in **app level build.gradle file:**

{% code title="build.gradle(app level)" %}
```groovy
android {

    //...
    //...
    
    compileOptions {
        sourceCompatibility JavaVersion.VERSION_1_8
        targetCompatibility JavaVersion.VERSION_1_8
    }
}
dependencies {
    //.. 
   implementation 'com.signzy:offlineaadhaar:<<VERSION>>'
}
```
{% endcode %}

Add the following code in your **AndroidManifest.xml** file:

{% code title="AndroidManifest.xml" %}
```markup
<provider
    android:name="androidx.core.content.FileProvider"
    android:authorities="/*your app's package name*/.provider"
    android:exported="false"
    android:grantUriPermissions="true">
    <meta-data
        android:name="android.support.FILE_PROVIDER_PATHS"
        android:resource="@xml/provider_paths" />
</provider>
```
{% endcode %}

Create an **XML** Android Source directory in the values directory and create a file with name **provider\_paths.xml** and paste the code given below:

{% code title="provider_paths.xml" %}
```markup
<?xml version="1.0" encoding="utf-8"?>
<paths>
    <external-path
        name="external_files"
        path="." />
</paths>
```
{% endcode %}

To open the SDK use the below code snippet:

### Java:

```java
Intent intent = new Intent(this, SignzyMainActivity.class);
intent.putExtra(SignzyMainActivity.SIGNZY_PARAMS, new SignzySdkParams(
        shareCode, /*Share Code*/,
        aadharNumber, /*aadharNo*/, /*Optional Parameter*/
        password, /*Password*/
        username, /*Username*/
        SignzyEnvironment.DEVELOPMENT /*Environment*/
));
startActivityForResult(intent, REQUEST_CODE);
```

### **Kotlin:**

```kotlin
val intent = Intent(this, SignzyMainActivity::class.java)
    .putExtra(
        SignzyMainActivity.SIGNZY_PARAMS, SignzySdkParams(
            zipCode = shareCode,
            aadharNumber = aadharNo,
            environment = SignzyEnvironment.DEVELOPMENT,
            username = "your_username",
            password = "password"
        )
    )
startActivityForResult(intent, REQUEST_CODE)
```

**SignzySdkParams** is a model class and it takes 5 parameters in its constructor.

1. **zipCode** is a 4-digit string value that will be the password of your Aadhaar zip file.
2. **aadharNumber** is a 12 digit string value as your aadhar card number, It is a optional parameter on which 2 of the result element depends i.e. aadharLast4DigitMatch & checksumMatch.
3. **password** is a string value provided by Signzy.
4. **username** is a string value provided by Signzy.
5. **SignzyEnvironment** is the **Environment** that is used to perform network requests in different Environments.
6.  **\*\*REMOVED\*\* storageType** is an enum type that **** specifies where you would like to save the Aadhaar zip file. If you specify **StorageType.PRIVATE** then the file will be stored in the private directory of your app and will be deleted if the app is deleted. The other option is **StorageType.PUBLIC** that will store the file in **Downloads** directory and will persist even if the app is uninstalled.&#x20;

    **If your app targets Android 11, both the WRITE\_EXTERNAL\_STORAGE permission and the WRITE\_MEDIA\_STORAGE privileged permission no longer provide any additional access.** use **StorageType.PRIVATE**



Currently, we provide two Environments:

* **SignzyEnvironment.DEVELOPMENT**
* **SignzyEnvironment.PRODUCTION**

### Results:

You need to override the **onActivityResult** method to get the results:

### Java:

```java
@Override
protected void onActivityResult(int requestCode, int resultCode, @Nullable Intent data) {
    if (requestCode == REQUEST_CODE) {
        if (resultCode == RESULT_OK) {
            if (data != null && data.getExtras() != null) {
                SignzySdkResponse response = data.getExtras().getParcelable(SignzyMainActivity.SIGNZY_RESULT);
                if (response != null) {
                    Log.d(TAG, "Response: " + response);
                    handleResponse(response);
                } else {
                    Toast.makeText(this, "Something went wrong", Toast.LENGTH_LONG).show();
                }
            }
        }

        if (resultCode == RESULT_CANCELED) {
            if (data != null && data.getExtras() != null) {
                String error = data.getExtras().getString(SignzyMainActivity.SIGNZY_ERROR);
                Log.d(TAG, "Error: " + error);
                Toast.makeText(this, error, Toast.LENGTH_LONG).show();
            }
        }
    }
    super.onActivityResult(requestCode, resultCode, data);
}
```

### Kotlin:

```kotlin
override fun onActivityResult(requestCode: Int, resultCode: Int, data: Intent?) {

    if (requestCode == CODE) {
        if (resultCode == Activity.RESULT_OK) {
            data?.extras?.let {
                val response =
                    it.getParcelable<SignzySdkResponse>(SignzyMainActivity.SIGNZY_RESULT)
                Log.d(TAG, "Response: $response")
                response?.let { result ->
                    handleResponse(result)
                } ?: Toast.makeText(this, "Something went wrong", Toast.LENGTH_LONG).show()
            }
        }
        if (resultCode == Activity.RESULT_CANCELED) {
            data?.extras?.let {
                Log.d(TAG, "Error: ${it.getString(SignzyMainActivity.SIGNZY_ERROR)}")
                Toast.makeText(
                    this,
                    "${it.getString(SignzyMainActivity.SIGNZY_ERROR)}",
                    Toast.LENGTH_LONG
                ).show()
            }
        }
    }
    super.onActivityResult(requestCode, resultCode, data)
}
```

**SignzySdkResponse** is a model class that exposes 2 parameters:

* **zipCode(String):** The shared code you passed while opening the SDK.
* **result(String):** The result of SDK.
* **filePath(String):** The path of the zip file which is downloaded on your device.

If you need the result in the form of the raw string, call **response.getResult()**.

```
{
   "address":"...",
   "dob":"...",                    // dd-mm-yyyy : Please note the hyphens instead of slashes
   "emailHash":"...",
   "gender":"...",
   "mobileNoHash":"...",
   "name":"...",
   "aadhaarLast4DigitMatch":true/false/null,
   "checksumMatch":true/false/null,
   "uid": "XXXXXXXX7425",
   "generationDate": "08/04/2021", // dd/mm/yyyy
   "generationTime": "22:54:04",   // HH:MM:SS
   "unixTimeStamp": 1617902644,    // Unix timestamp of generation.
   "photo":"...",                  // URL to the photograph of the individual
   "splitAddress":{
      "addressLine":"...",
      "city":"...",
      "country":"...",
      "district":"...",
      "pincode":"...",
      "state":"..."
   }
}
```

If you need the result in the form of a model class, you need to deserialize the string to get the model class. Use the following code to get model class from a string:

### Java:

```java
SignzyResult result = new Gson().fromJson(
                    sdkResponse.getResult(),
                    SignzyResult.class
            );
```

### Kotlin:

```kotlin
val model = Gson().fromJson<SignzyResult>(
        signzySdkResponse.result,
        SignzyResult::class.java
    )
```

### Known issues and other notable points

1. Signzy does not use the Read SMS permission as it is getting discontinued by Android. Instead, we make use of OTP receive prompt functionality provided by Android.
2. This functionality is tested to not work in some Samsung devices.
3. In devices where the OTP prompt is not received, the user would be required to fill in the OTP manually like in case the auto-filling functionality doesn't exist.
4. If dialog is being cancled before page load aadhar no. will not populate automatically

