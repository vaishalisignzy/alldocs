---
description: This page covers the description of custom settings
---

# Customizations

Various parts of UI can be customized based in the requirement matching the parent app

The following section defines the UI customization parameters.

The customization parameters can be passed with the intent that is invoking the activity, to do so add a intent extra value with name **docReaderParams** and pass **DocReaderParams** as the value.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
...

intent.putExtra(
    DocumentReaderActivity.DR_PARAMS,
    DocReaderParams( )
)

...
```
{% endtab %}

{% tab title="Java" %}
```java
...

intent.putExtra(
    "docReaderParams",
    new DocReaderParams()
)

...
```
{% endtab %}
{% endtabs %}

Signature for DocReaderParams class is as follows:&#x20;

{% hint style="info" %}
All the parameters are optional
{% endhint %}

All the parameters and their positions are explained in the images below:

```kotlin
DocReaderParams(
    // Global app background color
    val appBackground: Int = R.color.white,

    // Global app status bar color
    val statusBarColor : Int = R.color.blue_500,
    
    // Global app theme
    val theme : Int = R.style.Theme_DocReader,

    // Appbar customization params
    val logoImage: Int = R.drawable.sharp_wb_incandescent_24,
    val logoText: Int = R.string.dr_logo_text,
    val logoTextStyle : Int = R.style.DocReaderHeading6,

    // Landing Fragment Text
    val loadingDialogTitle : Int = R.string.dr_wait_text,
    val loadingDialogMsg: Int = 0,
    val loadingDialogBackground : Int = R.drawable.doc_reader_rounded_corners,
    val loadingDialogCancelText : Int = R.string.dr_cancel,
    val loadingDialogCancelStyle : Int = 0,

    // Permissions Fragment Text
    val userName: Int = R.string.dr_hey_user,
    val userNameStyle : Int = R.style.DocReaderHeading5,
    val userGreeting: Int = R.string.dr_user_greeting,
    val userGreetingStyle : Int = R.style.DocReaderSubtitle2Bold,
    val cameraDesc: Int = R.string.dr_camera_description,
    val cameraDescStyle : Int = R.style.DocReaderBody2,
    val grantButtonText: Int = R.string.dr_grant_access,
    val grantButtonStyle: Int = R.style.DocReaderButton,

    // Scanner
    val scannerTintColor : String = "#4D0089CC",
    val wait: Int = R.string.dr_wait_text,
    val waitStyle : Int = R.style.DocReaderSubtitle2Bold,
    val enableMultiPageProcessing: Boolean = false,
)
```

| Parameter                     | Type                    | Description                                                                                                                                                                                                                                    |
| ----------------------------- | ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **appBackground**             | Int (Resource Color)    | Global app background color                                                                                                                                                                                                                    |
| **statusBarColor**            | Int (Resource Color)    | Changes status bar color of sdk screens                                                                                                                                                                                                        |
| **theme**                     | Int (Resource Style)    | Targets the theme of the SDK. Be aware while using it, you may also require to change the **appBackground**, and styles of various other components mentioned below.                                                                           |
| **logoImage**                 | Int (Resource Drawable) | Logo image displayed on action bar                                                                                                                                                                                                             |
| **logoText**                  | Int (Resource String)   | Title displayed on action bar                                                                                                                                                                                                                  |
| **logoTextStyle**             | Int (Resource Style)    | Styling for title of action bar. (configure most of the things which works with textViews)                                                                                                                                                     |
| **loadingDialogTitle**        | Int (Resource String)   | title for loading dialog shown on landing screen                                                                                                                                                                                               |
| **loadingDialogMsg**          | Int (Resource String)   | description mesaage for loading dialog. By default it is 0 and SDK is setted such way that for O value it should not show **loadingDialogMsg**.                                                                                                |
| **loadingDialogBackground**   | Int (Resource Drawable) | Background of loading dialog shown on landing screen                                                                                                                                                                                           |
| **loadingDialogCancelText**   | Int (Rosource String)   | Cancel button text for loading dialog                                                                                                                                                                                                          |
| **loadingDialogCancelStyle**  | Int (Resource Style)    | Styling cancel button shown on loading dialog (configure most of the things which works with Buttons). By default it is 0 and SDK is setted such way that for O value it should not set any custom styling to cancel button of loading dialog. |
| **userName**                  | Int (Resource String)   | Text displayed on Permission Screen. For more better understanding refer to below images                                                                                                                                                       |
| **userNameStyle**             | Int (Resource Style)    | Styling for title of **userName**. (configure most of the things which works with textViews)                                                                                                                                                   |
| **userGreeting**              | Int (Resource String)   | Text displayed on Permission Screen below **userName**. For more better understanding refer to below images                                                                                                                                    |
| **userGreetingStyle**         | Int (Resource Style)    | Styling of **userGreeting**. (configure most of the things which works with textViews)                                                                                                                                                         |
| **cameraDesc**                | Int (Resource String)   | Description message which is being displayed for asking camera permission. For more better understanding refer to below images                                                                                                                 |
| **cameraDescStyle**           | Int (Resource Style)    | Styling of **cameraDesc** text. (configure most of the things which works with textViews)                                                                                                                                                      |
| **grantButtonText**           | Int (Resource String)   | Below **cameraDesc** text **grantButton** present, when pressed to it tries to ask camera permission. To change its text pass this parameter.                                                                                                  |
| **grantButtonStyle**          | Int (Resource Style)    | Styling of **grantButton**.(configure most of the things which works with Buttons)                                                                                                                                                             |
| **scannerTintColor**          | String                  | Changes color tint used for scanner. Pass color hex code in string here.                                                                                                                                                                       |
| **wait**                      | Int (Resource String)   | Opening scanner takes few seconds. So while its not opened as discription message displayed. To change its text pass this parameter.                                                                                                           |
| **waitStyle**                 | Int (Resource Style)    | Styling of **wait** text.(configure most of the things which works with TextView)                                                                                                                                                              |
| **enableMultiPageProcessing** | Boolean                 | By default false, Allows to process more than one page of the document (if they are exist) for several iterations.                                                                                                                             |

![Landing Screen](<../.gitbook/assets/cammand landing.png>)

![Permission screen](<../.gitbook/assets/cammand permission.png>)

![](<../.gitbook/assets/cammand wait.png>)

![Scanner](<../.gitbook/assets/cammand scanner.png>)
