# Introduction to Masters section



### API Hostname & Other Information <a href="#api-hostname-amp-other-information" id="api-hostname-amp-other-information"></a>

#### SIT: Signzy server <a href="#sit-signzy-server" id="sit-signzy-server"></a>

**Protocol:** https://

**Hostname:** indusind-dev.signzy.tech

**URL:** As per each API endpoint

#### UAT: IndusInd server <a href="#uat-indusind-server" id="uat-indusind-server"></a>

**Protocol:** http://

**Hostname:** indusind-reverse-proxy.signzy.app/indusind-server-uat

**URL:** As per each API endpoint

#### Production: IndusInd server <a href="#production-indusind-server" id="production-indusind-server"></a>

**Protocol:** https://

**Hostname:** indsig.indusind.com

### Front-End Master APIs <a href="#front-end-master-apis" id="front-end-master-apis"></a>

These Master APIs are used to perform CRUD (Create, read, update, delete) operations on database which will be then reflected on the front-end of the system i.e. Android Application.

Below is a collatted list of the available Front-end masters.

* Branch
* Cards
* Entity Document
* Dir-AS -Karta-Part-Doc
* Product
* Others Documents & Information
* RM Declaration
* Declaration
* Mode of Operation
* Form Field

### Back-End Master APIs <a href="#back-end-master-apis" id="back-end-master-apis"></a>

These Master APIs are used to perform CRUD (Create, read, update, delete) operations on database which will be used to process data for various functionalities collected from the front-end i.e. Android Application.

Below list details the masters used in the backend processing engine. Such masters are used to classify the data collected and accordingly execute certain actions based on implemented business logic.

* FV criteria
* FV
* Customer Profiler
* Green Channel Matrix
* Pincode
