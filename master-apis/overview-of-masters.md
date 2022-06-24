# Overview of Masters



### How to use this document <a href="#how-to-use-this-document" id="how-to-use-this-document"></a>

This document should be used as a reference for consuming **IndusInd Master APIs**. The section that is right side in the documentation contains the JSON requests and responses. The central column on this page will help you with detailed information about each endpoint. API documentations corresponding to the other API endpoints, like push by LMS will be added in this document eventually. This documentation will also be used as host of other endpoint details. This API documentation is a work in progress and certain changes can be expected in the same as project evolves, to cater to increased performance and better organisation of APIs. The changes done shall be communicated separately too.

### Important note <a href="#important-note" id="important-note"></a>

The data entered into the Masters database using these APIs is consumed by the Android application to configure display in the end user android devices. Examples of configurable elements are:

1. Dropdowns
2. Cards
3. Products
4. Declarations
5. Documents etc
6. Forms

&#x20;The changes made in the below APIs are directly reflected on the Android Application. Users should take utmost care while entering and removing data from the application. The endpoints provided below are working without authentication since this is a alpha release, in a dummy app format. Eventually the endpoints will be secured using credentials level Basic Auth. The credentials can be availed separately over email from the Signzy team.

### Basic details about the APIs <a href="#basic-details-about-the-apis" id="basic-details-about-the-apis"></a>

#### Entity Name To Entity Code Mapping <a href="#entity-name-to-entity-code-mapping" id="entity-name-to-entity-code-mapping"></a>

* 001 - Proprietor
* 002 - Company
* 003 - LLP
* 004 - Registered Partnership
* 005 - Unregistered Partnership
* 006 - Individual
* 007 - One Person Comapany
