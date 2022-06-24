---
description: >-
  This page describes the APIs related to the dataset module. The frontend code
  hits these apis and interacts with the backend using these endpoints.
---

# Dataset backend APIs

{% swagger baseUrl="https://staging-ai.signzy.xyz/nebula/backend" path="/dataset/list" method="get" summary="Dataset List API" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Authentication token is required to check which user is hitting this endpoint.
{% endswagger-parameter %}

{% swagger-response status="200" description="List of dataset objects, containing name, count of number of images in the dataset, date the dataset was created, date dataset was updated, combined size of all images in the dataset, creator of the dataset." %}
```
{
    "result": {
        "datasetList": [
            {
                "uniqueID": "60a615cba968f97e6ca568f1",
                "name": "Aadhaar Dataset",
                "imagesCount": 16414,
                "uploadDate": "2021-05-20 07:54",
                "modifyDate": "2021-05-20 07:54",
                "datasetSize": "6138.25MB (6.0GB)",
                "createdBy": "vedant"
            },
            {
                "uniqueID": "60a6236aa968f955057c6fce",
                "name": "PAN Dataset",
                "imagesCount": 6363,
                "uploadDate": "2021-05-20 08:52",
                "modifyDate": "2021-05-20 08:52",
                "datasetSize": "1878.31MB (1.8GB)",
                "createdBy": "vedant"
            },
            {
                "uniqueID": "60a626cba968f954f9a92b91",
                "name": "Indian Passport",
                "imagesCount": 4717,
                "uploadDate": "2021-05-20 09:07",
                "modifyDate": "2021-05-20 09:07",
                "datasetSize": "735.76MB (735.8MB)",
                "createdBy": "vedant"
            }
        ]
    }
}
```
{% endswagger-response %}

{% swagger-response status="400" description="If anything unexpected goes wrong, API returns a 400 status code." %}
```
{
    'message': 'Unknown error.',
    'status':400, 
    'name': 'Unknown error'
}
```
{% endswagger-response %}

{% swagger-response status="401" description="If the authorisation token verification fails, then API returns a 401 with error message." %}
```
{
    'message': 'Invalid Authentication.',
    'status':401, 
    'name': 'Unauthorised request.'
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://staging-ai.signzy.xyz/nebula/backend" path="/dataset/create" method="post" summary="Dataset Create API" %}
{% swagger-description %}
The dataset create API uses multipart form data as input through a POST request. 

\


The dataset folder is created and internally the upload function uses multi threading to concurrently calculate image parameters (size, resolution, image hash, etc) and saves them to the mongodb, it also uploads images to persist and saves to local copy to the trove folder.
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
Authentication token is required to check which user is hitting this endpoint.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Image(s)" type="object" %}
Image data sent as part of the multipart request body
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Dataset Name" type="string" %}
name of the dataset (can contain spaces and symbols)
{% endswagger-parameter %}

{% swagger-response status="200" description="API returns a unique datasetID, number of successful file uploads and for any reason if any files are not uploaded then number of files that failed to upload. " %}
```
{
	"datasetID":"60a615cba968f97e6ca568f1",
	"success": "10 files uploaded.",
	"status":200, 
	"failedUpload":"0",
	"successUpload":"10"
}
```
{% endswagger-response %}

{% swagger-response status="400" description="If anything unexpected goes wrong, API returns a 400 status code." %}
```
{
    'message': 'Unknown error.',
    'status':400, 
    'name': 'Unknown error'
}
```
{% endswagger-response %}

{% swagger-response status="401" description="If the authorisation token verification fails, then API returns a 401 with error message." %}
```
{
    'message': 'Invalid Authentication.',
    'status':401, 
    'name': 'Unauthorised request.'
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://staging-ai.signzy.xyz/nebula/backend" path="/dataset/details" method="post" summary="Dataset Details API" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="Authorization" type="string" %}
Authentication token is required to check which user is hitting this endpoint.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="id" type="string" %}
Dataset ID is required to fetch all details related to this dataset from the backend.
{% endswagger-parameter %}

{% swagger-response status="200" description="Dataset details API returns general api details, and an array containing metadata and urls of all images stored in that dataset." %}
```javascript
{
    "result": {
        "datasetDetails": {
            "uniqueID": "60f6c0d0a968f9132ebf6b00",
            "name": "testRuleSet3",
            "imagesCount": 3,
            "uploadDate": "2021-07-20 17:55",
            "modifyDate": "2021-07-20 17:55",
            "datasetSize": "  1.98MB (2.0MB)",
            "createdBy": "yash"
        },
        "datasetDetilsRows": [
            {
                "uniqueID": "60f96ed7a968f933146bfc15",
                "name": "PxtaOARjrhTJkWN4tVV2FTRGJJ0nPKyH.png",
                "fileSize": "0.91MB (934.8KB)",
                "imageSize": "3505x2480",
                "uploadDate": "2021-07-22 18:42",
                "fileType": "PNG",
                "uploadedBy": "yash",
                "url": "https://preproduction-persist.signzy.tech/api/files/26936493/download/4cac5898807f4daab74bc7ce09aef1f537ed91ac9c8b4cf9903c9e614e1123db.png"
            },
            {
                "uniqueID": "60faa114a968f949396452c4",
                "name": "46zvItWZL8NV5MkMCYbNXMI0aUATf2PP.jpg",
                "fileSize": "0.48MB (487.8KB)",
                "imageSize": "2560x1876",
                "uploadDate": "2021-07-23 16:29",
                "fileType": "JPG",
                "uploadedBy": "yash",
                "url": "https://preproduction-persist.signzy.tech/api/files/26953739/download/01f84fa9b3d64afdac77d9c0a621abc176fecc9d3af748deb5159651b5d9954b.jpg"
            },
            {
                "uniqueID": "60feccfaa968f914340045d9",
                "name": "PdOKrphYooabEttxNCeAnnWlkYWVoNZ0.jpg",
                "fileSize": "0.59MB (606.2KB)",
                "imageSize": "3092x2339",
                "uploadDate": "2021-07-26 20:25",
                "fileType": "JPG",
                "uploadedBy": "yash",
                "url": "https://preproduction-persist.signzy.tech/api/files/26968725/download/d71c5888c5204f94b53b6daff1d84437c1f962b1d89a4bf9baa547e0be8d97bb.jpg"
            }
        ]
    }
}
```
{% endswagger-response %}

{% swagger-response status="400" description="If anything unexpected goes wrong, we return 400" %}
{% tabs %}
{% tab title="Unknown error" %}
```javascript
{
    'message': 'Unknown error.',
    'status':400, 
    'name': 'Unknown error'
}
```
{% endtab %}

{% tab title="Invalid JSON" %}
```
{
	'message': 'invalid JSON syntax.',
	'status':400, 
	'name': 'Invalid JSON sent to to /nebula/backend/dataset/details'
}
```
{% endtab %}

{% tab title="Invalid Body Parameters" %}
```
{
	'message': 'Invalid JSON parameters.',
	'status':400, 
	'name': 'Invalid input parameters to /nebula/backend/dataset/details'
}
```
{% endtab %}

{% tab title="Dataset does not exist" %}
```
{
	'message': 'Invalid JSON parameters.',
	'status':400, 
	'name': 'Invalid input parameters to /nebula/backend/dataset/details'
}
```
{% endtab %}
{% endtabs %}
{% endswagger-response %}

{% swagger-response status="401" description="Invalid authorisation token returns 401." %}
```javascript
{
    'message': 'Invalid Authentication.',
    'status':401, 
    'name': 'Unauthorised request.'
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://staging-ai.signzy.xyz/nebula/backend" path="/delete/images" method="post" summary="Delete Image from Dataset" %}
{% swagger-description %}
This api removes the image object from the images collection from mongodb, and removes the local copy from the dataset folder which is present in the "trove" folder. The API returns an array containing updated set of images in the dataset.
{% endswagger-description %}

{% swagger-parameter in="path" name="Authorization" type="string" %}
Auth token is required to check which user is hitting the endpoint and to check privileges.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="imagesNames" type="array" %}
This is an array of strings, containing the image names that need to be deleted.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="datasetID" type="string" %}
unique id associated with the dataset from which the  images need to be deleted.
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "datasetDetails": {
    "uniqueID": "6128d893a968f9318ca55863",
    "name": "Sample Csv Annotation",
    "imagesCount": 2,
    "uploadDate": "2021-08-27 17:50",
    "modifyDate": "2021-08-27 17:50",
    "datasetSize": "  1.02MB (1.0MB)",
    "createdBy": "vedant"
  },
  "datasetDetilsRows": [
    {
      "uniqueID": "6128d896a968f9318ca55864",
      "name": "EsequZhULgABRq1CPbzDl5IGdE6PsmZK.png",
      "fileSize": "0.85MB (866.0KB)",
      "imageSize": "2381x1650",
      "uploadDate": "2021-08-27 17:50",
      "fileType": "PNG",
      "uploadedBy": "vedant",
      "url": "https://preproduction-persist.signzy.tech/api/files/27453655/download/5f88e03ccdf946659d2c374845c004367f6355e0b2f042fe917fbf655d07d62e.png"
    },
    {
      "uniqueID": "6128d896a968f9318ca55866",
      "name": "k4Yg0BdMJtt8ux4KX7ISMIRlwib3eJJV.jpg",
      "fileSize": "0.11MB (115.1KB)",
      "imageSize": "1200x1600",
      "uploadDate": "2021-08-27 17:50",
      "fileType": "JPG",
      "uploadedBy": "vedant",
      "url": "https://preproduction-persist.signzy.tech/api/files/27453595/download/ecf205987df8477baaf00b6fc20eea578f3d15e6ef2b4322aca3b12337dcbdc6.jpg"
    }
  ]
}
```
{% endswagger-response %}

{% swagger-response status="400" description="" %}
{% tabs %}
{% tab title="Invalid JSON" %}
```
{
	'message': 'invalid JSON syntax.',
	'status':400, 
	'name': 'Invalid JSON sent to to /nebula/backend/dataset/delete/images'
}
```
{% endtab %}

{% tab title="Invalid Parameters" %}
```
{
	'message': 'Invalid JSON parameters.',
	'status':400, 
	'name': 'Invalid input parameters to /nebula/backend/dataset/delete/images'
}
```
{% endtab %}

{% tab title="Dataset does not exist" %}
```
{
	'message': 'Invalid JSON parameters.',
	'status':400, 
	'name': 'Invalid input parameters to /nebula/backend/dataset/delete/images'
}
```
{% endtab %}
{% endtabs %}
{% endswagger-response %}

{% swagger-response status="401" description="" %}
```
{
	'message': 'Invalid Authentication.',
	'status':401, 
	'name': 'Unauthorised request.'
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://staging-ai.signzy.xyz/nebula/backend" path="/dataset/update" method="post" summary="Update Dataset API (upload more images)" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="Authorization" type="string" %}
Auth token is required to check which user is hitting the endpoint and to check privileges.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Dataset name" type="string" %}
Unique dataset name (to identify which dataset to upload to)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Image(s)" type="string" %}
image data sent as part of the multipart request body
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
	"datasetID":"60a615cba968f97e6ca568f1",
	"success": "10 files uploaded.",
	"status":200, 
	"failedUpload":"0",
	"successUpload":"10"
}
```
{% endswagger-response %}

{% swagger-response status="400" description="" %}
```
{
    'message': 'Unknown error.',
    'status':400, 
    'name': 'Unknown error'
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger baseUrl="https://staging-ai.signzy.xyz/nebula/backend" path="/dataset/download" method="post" summary="Download Dataset (image urls in csv)" %}
{% swagger-description %}
Fetch image urls from mongodb and create a csv writer object and fill it with image urls belonging to the dataset ID sent the the request body.
{% endswagger-description %}

{% swagger-parameter in="path" name="Authorization" type="string" %}
Auth token required to check user privileges and log which user is hitting the api
{% endswagger-parameter %}

{% swagger-parameter in="body" name="datasetID" type="string" %}
unique datasetID
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
{% code title="Table-<datasetid>.csv" %}
```
url
https://preproduction-persist.signzy.tech/api/files/25870407/download/fff09f1b83e24154a2949b283abe12959a4c88077b3c4079a0ba70e25dd4749f.jpeg
https://preproduction-persist.signzy.tech/api/files/25870421/download/00393a6b2e324c7f9a93b7f662adaefd5c1adfe46b2e4fd0983b67d5ca4d1f07.jpeg
https://preproduction-persist.signzy.tech/api/files/25870425/download/f773e695d0bd49d0a1c37cd87e8464bfecfda40935a3482ebb269a5d7cf9fc47.jpeg
https://preproduction-persist.signzy.tech/api/files/25870427/download/1b825ecba74e45caad992edb74c5fc659d61e2ac7085414e9c6c41fc5267d675.jpeg
https://preproduction-persist.signzy.tech/api/files/25870429/download/0449eb9951414240a215a6a68f0c6e4ce8ffd25036af4e589e65b881b6e6c581.jpeg
```
{% endcode %}
{% endswagger-response %}
{% endswagger %}
