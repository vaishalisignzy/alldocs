---
description: >-
  This document is all about the installation and other workaround of the
  application
---

# Mobile Application

## Installation

* Download the Intelligent HUB From play store \[[LINK](https://play.google.com/store/apps/details?id=com.airwatch.androidagent\&rdid=com.airwatch.androidagent)]
* Open Intelligent HUB, enter domain as [deviceuat.indusind.com](http://deviceuat.indusind.com/)
* Login with your credentials, then go to the App Catalogue
* Install _IndusCorporate_ from the list

## Some walkthroughs

{% hint style="info" %}
In the create entity page, if either ‘Sub segment’ or the ‘Mode of operation’ dropdown doesn't show any values, then their corresponding master data is empty or not present for that particular entity. This will now not let the journey to continue.
{% endhint %}

{% hint style="info" %}
In all the business proof if the address does not contain a _pincode_ then it’s converted to an editable field and marked as a WEAK proof

The dropdown values of all the ‘other’ radio button for communication address is fetched from the master, so any change in data in masters will be reflected there.

In case of Authorised Signatory forms section, for a particular mode of operation if there is no debit card then the option to select debit card is hidden, irrespective of subsegment master’s control variable.
{% endhint %}

{% hint style="info" %}
App level validations will only be executed when the fields are non empty. Example, in case of address, when address is entered then only it will be validated, else it won't be.
{% endhint %}

{% hint style="info" %}
The data in IP Cheque Validation page will only be saved when then IMPS Verification API is called, and it gets called only when data like Account number, IFSC Code, Bank name are given. If image is being uploaded after filling the data, then all the extracted data will get over the earlier entered data, so it is recommended to first upload the image of cheque to get the extracted OCR data.\


The emails for signatory details, to the selected signatory will be sent only after generating contract in the application.
{% endhint %}
