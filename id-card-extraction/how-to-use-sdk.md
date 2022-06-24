---
description: This page covers the description of the starting SDK and its results.
---

# How to use SDK

## Starting SDK

The use of the ID-CARD-EXTRACTION module can be performed fully offline. The IdCardExtractionActivity is a class that starts SDK. On opening, SDK initializes and on very first open shows Instruction screen along with asking camera permission if not granted. To open SDK you have to invoke an intent for the activity: **IdCardExtractionActivity**.

Here is an example of how to perform initialization:

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
fun startIdCardExtraction() {
 val intent = Intent(requireContext(), IdCardExtractionActivity::class.java)
 intent.putExtra(IdCardExtractionActivity.EXT_SIGNZY_API_KEY, "<<EXT_API_KEY>>")
 intentLauncher.launch(intent)
}


private val intentLauncher = registerForActivityResult(
            ActivityResultContracts.StartActivityForResult()
) { result ->
            
}
```
{% endtab %}

{% tab title="Java" %}
```java
void startIdCardExtraction() {
    Intent intent = new Intent(Activity, IdCardExtractionActivity.class)
    intent.putExtra(IdCardExtractionActivity.EXT_SIGNZY_API_KEY, "<<API_KEY>>")
    intentLauncher.launch(intent)
}


ActivityResultLauncher<Intent> intentLauncher = registerForActivityResult(new StartActivityForResult(),
        new ActivityResultCallback<ActivityResult>() {
    @Override
    public void onActivityResult(ActivityResult result) {
        
    }
});
```
{% endtab %}
{% endtabs %}

Here _**EXT\_API\_KEY**_** ** will be provided by Signzy and you should pass this key every time you call this activity else it will give the result _**EXT**_**\_**_**RESULT\_ERROR\_KEY**_**\_**_**MISSING.**_

## **Results**

The results are returned in **intentLauncher** defined above once SDK completes its extractions or the user performs some action.

### Result Codes

SDK returns the following result codes depending on what happened during the flow of SDK

| Result Code                                  | Description                                                                                                                                                                                                                                               |
| -------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **EXT\_RESULT\_SUCCESS**                     | If all things go well and SDK has successfully extracted data this result code will be sent. Here data will be sent in parcelable object **ExtractionDetails** which you can get from result intent using key **ExtractionDetails.EXT\_RESULT\_DETAILS**. |
| **EXT\_RESULT\_CANCELED**                    | This code is sent when the user has pressed the close/back button during the flow                                                                                                                                                                         |
| **EXT\_RESULT\_FAILED**                      | Code sent when SDK is failed to extract data from the provided ID card. Also, this code is sent when the user is not placing any ID card in front of the Scanner. But the SDK still sends images of the captured object inside **ExtractionDetails**.     |
| **EXT\_RESULT\_ERROR\_PERMISSION**           | SDK requires camera permission and if permission is not granted so it tries to ask permission but if the user pressed '_DENY_' or '_DENY & DON'T ASK AGAIN_'. So this result code is sent.                                                                |
| **EXT\_RESULT\_ERROR\_ADDITIONAL\_DATA**     | If additional String data passed in intent with key _**EXT\_ADDITIONAL\_DATA** _ length is more than 1024 characters than this result code is sent.                                                                                                       |
| **EXT\_RESULT\_ERROR\_KEY\_MISSING**         |  You should pass this _**EXT\_SIGNZY\_API\_KEY**_ every time you call this activity else it will give the result _**EXT**_**\_**_**RESULT\_ERROR\_KEY**_**\_**_**MISSING.**_                                                                              |
| **EXT\_RESULT\_ERROR**                       | If something went wrong while executing the SDK so then this code is sent.                                                                                                                                                                                |
| **EXT\_RESULT\_ROOTED**                      | SDK does not support rooted devices, so if it finds that user device is rooted it sends this result.                                                                                                                                                      |
| **EXT\_RESULT\_ERROR\_VERIFICATION\_FAILED** | This means you had provided wrong API key.                                                                                                                                                                                                                |
| **EXT\_RESULT\_ERROR\_BLOCKED**              | If Relationship between you and Signzy fall apart then this result code will be sent by SDK                                                                                                                                                               |

Here is an example of how to check results:

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
private val intentLauncher = registerForActivityResult(
            ActivityResultContracts.StartActivityForResult()
) { result ->
 if(result.resultCode == IdCardExtractionActivity.EXT_RESULT_SUCCESS) {
   val details: ExtractionDetails? =
       result.data?.getParcelableExtra(IdCardExtractionActivity.EXT_RESULT_DETAILS)

   if (resultData != null) {
        // Save or use the result
        
        val extractedAttributes = details.extractedAttributes
        val resultBitmaps = details.resultBitmaps
        val pageBitmaps = details.pageBitmaps
        val cardValid = details.isCardValid
        val cardType = details.cardType
    }
 }           
}
```
{% endtab %}

{% tab title="Java" %}
```java
ActivityResultLauncher<Intent> intentLauncher = registerForActivityResult(new StartActivityForResult(),
        new ActivityResultCallback<ActivityResult>() {
    @Override
    public void onActivityResult(ActivityResult result) {
        if (result.resultCode == EXT_RESULT_SUCCESS) {
            Parcelable<ExtractionDetails> resultData = result.getData().getParcelableExtra<ExtractionDetails>(EXT_RESULT_DETAILS)

            if (resultData != null) {
            // Save or use the result
            
                HashMap<Integer, HashMap<String, String>> extractedAttributes = details.getExtractedAttributes();
                HashMap<Integer, Bitmap> resultBitmaps = details.getResultBitmaps();
                ArrayList<Bitmap> pageBitmaps = details.getPageBitmaps();
                boolean cardValid = details.isCardValid();
                String cardType = details.getCardType();

            }
        }
    }
});
```
{% endtab %}
{% endtabs %}

### ExtractionDetails

You can use following getters to get Extraction Results for ExtractionDetails class

#### **cardType : String**

It gives the return value of type String, Different types of values returned by this method are mention below:

| **Type**                              | Description         |
| ------------------------------------- | ------------------- |
| **EXT\_CARD\_TYPE\_PASSPORT**         | Passport            |
| **EXT\_CARD\_TYPE\_AADHAAR**          | Aadhaar Card        |
| **EXT\_CARD\_TYPE\_INDIVIDUAL\_PAN**  | Individual Pan Card |
| **EXT\_CARD\_TYPE\_BUSINESS\_PAN**    | Business Pan Card   |
| **EXT\_CARD\_TYPE\_DRIVING\_LICENSE** | Driving License     |
| **EXT\_CARD\_TYPE\_VOTER\_ID**        | Voter ID            |
| **EXT\_CARD\_TYPE\_UNKNOWN**          | Unknown             |

#### ****

#### **extractedAttributes** : HashMap\<Integer, HashMap\<String, String>>

It gives the return value of type Hash-map, where the key is of type Integer. If the only front of the document is captured then It will consist single key-value pair where the key will be 0 and if the front and back are both captured, then the photo which is captured first will be stored with 0 and the second with the key 1. Each value of this returned HashMap is also a HashMap which has key and value both of type String. Key is the Name of the field and Value is extracted data.

#### **resultBitmaps** : HashMap\<Integer, Bitmap>

It gives the return value of type Hash-map, where the key is of type Integer. If the only front of the document is captured then It will consist single key-value pair where the key will be 0 and if the front and back are both captured, then the photo which is captured first will be stored with 0 and the second with the key 1. Each value of this returned HashMap is a Bitmap which is Captured Image while extraction.

#### **pageBitmaps** : ArrayList\<Bitmap>

It gives the return value of type ArrayList, Each value of this returned ArrayList is a Bitmap which is Captured Image while extraction.

#### isCardValid : Boolean

It gives the return value of type Boolean, If true received means SDK identified scanned ID card as valid.

