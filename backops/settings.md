# Settings

## **URL Configuration**

![](https://lh4.googleusercontent.com/qpwLuaQkVVh85hdNNnLAiKlvuvs0UF7m1n85heVnHLim-Fe14V4MBbcQaOaD2tK1HxV2-LCZre\_9Q9tjOF13ml8eVgmiWRq3nQf8J61LLi-dFKow2sT88Ndzd3m3NG6VQXudVJ-UKhl8GcL7iQ)

## **Decision and Mail Configuration**

In this section, you can customise the look of the window of application reject, drafts, accept etc.&#x20;

* Provide an alias i.e., the title that will be shown to the user.&#x20;
* To change the colour of the header, enter the hex code of the colour (for eg., #78dndk8)
* A default subject for all the mails that will be sent&#x20;
* A default message, so that you don’t have to type again and again for the same reasons.
* Reasons to reject/ draft. The reasons must be separated by the comma. Enter the sender’s email address.

![Decision and Mail Config](https://lh5.googleusercontent.com/yGpWC1dSRK1ObC0RuWIN5\_kZ7gxZzY8cvNUKj6fVNAEkzXygQN3DZyd6nmNR2kSsGfGOZsoYr2sjM8A3EUrD45mT1umn3Fo30USOH9VUsJNANIKcFH4LUu1jY6L1zgY6TS2lfVAC\_86N4ZP6rQ)

## **Custom Backops forms**

Here, the user can create a setting. Add the setting name and select a flow.

In select flow, You can either select all flows or certain flows in which to create a setting.

We have five blocks under the select flow and they are:

* Escalate&#x20;
* Accept&#x20;
* Reject&#x20;
* Draft&#x20;
* Internal Notes

**Fill in the necessary information and click on ‘Create Form**

![](https://lh5.googleusercontent.com/Lp1-hisAg50ZUFY2QLCjcQ3QXDiNcDoWY0raVZitQ4pqgaOpRuqL1oGJ\_Qvzgv1fhJUz1ytCx5Idk2zgmePemT6Klq45PqRDoHmcp9d6jYqRHgwmBm3vnbSNDRlCIGxcEL3KKBYYepu5l5KlfQ)

## **Internal Dedupe**

#### What is Internal Dedupe?&#x20;

Internal Dedupe is a feature to check whether the application already exists in the system or not. Dedupes can also help RMs assess the quality of the application or the record of the applicant.&#x20;

A positive result can help cut short the time for the onboarding by prefilling the data into the application.

#### **How to work with it?**

The Option to enable Dedupe can be provided under the Setting tab within the Backops screen. The user can enable the dedupe option for the flow existing in the GO Admin account.

The user can select anyone from the 3 parameters for dedupe:

* Name of merchant/applicant and mobile number&#x20;
* PAN Card of individual or entity&#x20;
* Mobile number&#x20;
* Any merchant variable can be used for the same.

{% hint style="info" %}
Since PAN is not a mandatory field in the application/merchant creation we can keep a custom variable that we can use to search for duplication within applications.
{% endhint %}

![Internal Dedupe](https://lh3.googleusercontent.com/NvNv4ax\_b-esjVXsi\_Qy6UomnoOqA9Vd9LYspyIw834uFmtm3omkKe\_icRjn1tZeRqBXnF24rtCL8B2abcGsm3RV6uH3V5Ta8PlnooI75eE\_dmB4uf13ocLSEZNd3HuWQIwZLHqfaZy5JbPRLw)

### **How can this help?**

There can be scenarios where an internal dedupe can be used.

* If there is an existing application for a new merchant being created. The RM or the applicant can use the data to prefill the application and save a lot of effort.&#x20;
* If the dedupe is positive RM can be suggested whether proceed or not, depending on the checker’s comment of the previous application.&#x20;
* If the dedupe is positive then it can be brought to RM’s notice that an application of the same applicant exists in the system.

### **DIY Scenarios**

* If there is an existing application for a new merchant being created. The RM or the applicant can use the data to prefill the application and save a lot of effort.&#x20;
* If there is an application that has been found in the dedupe and the application was in pending or draft state, the same can be used to reactivate the previous application(grant based).

### Dedupe Parameters

* Name/username of merchant/applicant and mobile number&#x20;
* PAN Card of individual or entity&#x20;
* Mobile number&#x20;
* Any merchant variable can be used for the same.

### **Configuring Dedupe in Admin**

The Option to enable Dedupe can be provided under the Setting tab within the Backops screen. The user can enable the dedupe option for the flow existing in the GO Admin account.&#x20;

The user can select anyone from the 3 parameters for dedupe:&#x20;

1. Name of merchant/applicant and mobile number&#x20;
2. PAN Card of individual or entity&#x20;
3. Mobile number&#x20;

Any merchant variable can be used for the same

{% hint style="info" %}
Since PAN is not a mandatory field in the application/merchant creation we can keep a custom variable that we can use to search for duplication within applications.
{% endhint %}

****

**Prefilling the application from a dedupe positive result:**

* Prefill the data and keep the fields editable&#x20;
* Prefill the data and the data cannot be edited

**Edge Scenarios**

* For dedupe across flow how will data mapping happen and how will the data be prefilled.&#x20;
* In case the journey(configuration changes)

## **Backops Grant Configuration**

When you open an application for review (in Backops), you'll see certain tabs. From here, you can configure which tabs you want to show.&#x20;

For example, If a journey does not have VKYC, you can remove the forensics tab from here, as it is not required.

![](https://lh3.googleusercontent.com/338qh8UL9yFv\_vp-GHDkYb9ov32tofktLx9LiuO1AxpkakC4z\_UkOelleUj1QIPO9v2U6mOGP\_SkUSfHEGXh0mbjrWqkq5v7SYr2VounTymt5AkPi-S29Pc\_XyKGZFU\_k\_vdqw3TIVDDm1YjQw)

## **Backops level Configuration**

If there is a hierarchy in your organisation, you can define the levels here. For eg., if there is an application and the number of levels defined is 3, the application has to be approved by all 3 levels to pass the check.&#x20;

You can define the maximum levels here. These levels are then reflected in the Backops portal (Manage Roles).

![Levels](https://lh3.googleusercontent.com/1O43B3noGfwwhTXJ22sRWFf\_H4rDTPqUxxn0sd7QVyVOd81-sSTBp8KClwAQXoR0YO\_CoaP1mVsMi4D9tUd7mXOtDqv4x4mRRDRIWng9ks5BfSza2UDiXJtfv5FerRL4ZUQSCEcCAyntPqi0AQ)

## **Backops User Configuration**

#### What is Dormancy?&#x20;

It is a state of rest or inactivity; inoperative. **** If you have enabled dormancy, and the user has not logged in since two days(mentioned here) then the login credentials of that user will be automatically deactivated.&#x20;

Then the manager of the Backops user will have to activate the credentials of the user by using Backops Portal.

![](https://lh4.googleusercontent.com/aYOi8C8wEnbwjG4tO29AQglhgHZYfOeZLErE\_V-Ge4WaBvQn5\_LHlyBBOtdJtra\_-DqiBuNKMPW-IUUCBK5i-LfZL1T53D27ryuoJOax5XkwA6ZyUJ1MegHLvQUv2ILQrSPS\_cFyh8A\_HQ60Aw)

## **Application Card Configuration**
