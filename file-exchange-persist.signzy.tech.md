# File Exchange - persist.signzy.tech

Signzy brings to customers a unique file upload system, persist.signzy.tech, which can be used to upload ID cards and documents to get a direct URL. This can be further made use by our API services as the API’s do not need to manually upload the documents, rather just attach the direct URL which can later be used for further verification.

The URLs expire in 30 seconds by default, unless explicitly specified in the inbound request in the ttl parameter.

## Multi-part form data based file upload

This is the basic form for accepting image based data, mostly in jpeg format

* Request data :: multipart-form-data with  & optional text properties ttl, optimize and key
* ttl accepts the following values: (2 mins, 10 mins, 30 mins, 2 hrs, 12 hrs, 7 days, 15 days, 1 month, 3 month, 6 month, 1 year, 3 years, infinity)
* optimize true reduces the size of the file before uploading, only images are supported with the optimize property
* key is an alphanumeric string which can be used to protect the file. The file will not be downloaded without passing the correct key
* File size limit is 100Mb
* If multiple parameters with the same name are passed/uploaded, the first ones are considered



{% swagger baseUrl="https://preproduction-persist.signzy.tech" path="/api/files/upload" method="post" summary="Multi part Form Data File Upload" %}
{% swagger-description %}
Production URL:

\




`https://persist.signzy.tech/api/files/upload`
{% endswagger-description %}

{% swagger-parameter in="body" name="file" type="object" %}
file will be uploaded via multipart formdata
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ttl" type="string" %}
Time-To-Live for the file
{% endswagger-parameter %}

{% swagger-parameter in="body" name="optimize" type="string" %}
optimize true reduces the size of the image file before uploading
{% endswagger-parameter %}

{% swagger-parameter in="body" name="key" type="string" %}
An alphanumeric string to protect the file. If this is passed, the file cannot be downloaded without this
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
      "file": {
        "id": "...id...",
        "filetype": "...mimeType...",
        "size": size,
        "directURL": "https://persist.signzy.tech/api/files/...id.../download/...name...",
        "protected": true/false
    }
}
```
{% endswagger-response %}
{% endswagger %}

## Base64 based - form data file upload

### Input parameters

#### Form data should have the following parameters.

* base64string : This is mainly used to retrieve 'base64 of the file'
* mimetype: :Used to get  'mime type eg (image/jpeg)'
* ttl: This parameter accepts the following values:(2 mins, 10 mins, 30 mins, 2 hrs, 12 hrs, 7 days, 15 days, 1 month, 3 month, 6 month, 1 year, 3 years)

{% swagger baseUrl="https://preproduction-persist.signzy.tech" path="/api/base64strings/upload" method="post" summary="Base64 File Upload" %}
{% swagger-description %}
Production URL:

\




`https://persist.signzy.tech/api/base64strings/upload`
{% endswagger-description %}

{% swagger-parameter in="body" name="base64string" type="string" %}
Base64 String of the Image
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ttl" type="string" %}
Time-To-Live for the file
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mimetype" type="string" %}
Mime Type of the Image
{% endswagger-parameter %}

{% swagger-parameter in="body" name="key" type="string" %}
An alphanumeric string to protect the file. If this is passed, the file cannot be downloaded without this. 
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
      "file": {
        "id": "...id...",
        "filetype": "...mimeType...",
        "size": size,
        "directURL": "https://persist.signzy.tech/api/base64strings/...id.../download/...name...",
        "protected": true/false
     }
}
```
{% endswagger-response %}
{% endswagger %}



## Base64 JSON based file upload

Input parameters

JSON POST request with the following parameters as part of input

* base64String : 'base64 of the file with 100Mb size limit'
* mimetype: : 'mime type possible types: (image/jpeg, image/png, image/jpg, application/pdf)'
* ttl: Accepts the following values: (2 mins, 10 mins, 30 mins, 2 hrs, 12 hrs, 7 days, 15 days, 1 month, 3 month, 6 month, 1 year, 3 years, infinity). Default value, if invalid ttl is passed is 30 secs.

{% swagger baseUrl="https://preproduction-persist.signzy.tech" path="/api/base64" method="post" summary="JSON Based Upload" %}
{% swagger-description %}
Production URL:

\




`https://persist.signzy.tech/api/base64`
{% endswagger-description %}

{% swagger-parameter in="body" name="base64String" type="string" %}
Base64 String of the Image
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ttl" type="string" %}
Time-To-Live for the file
{% endswagger-parameter %}

{% swagger-parameter in="body" name="mimetype" type="string" %}
Mime type of the image
{% endswagger-parameter %}

{% swagger-parameter in="body" name="key" type="string" %}
An alphanumeric string to protect the file. 
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
      "file": {
        "id": "...id...",
        "filetype": "...mimeType...",
        "size": size,
        "directURL": "https://persist.signzy.tech/api/files/...id.../download/...name...",
        "protected": true/false
     }
}
```
{% endswagger-response %}
{% endswagger %}

## Response Parameters

| Parameter Name | Description                                                  |
| -------------- | ------------------------------------------------------------ |
| file.id        | Unique Identifier for the File                               |
| file.filetype  | The mime type of the File                                    |
| file.size      | Size of the file                                             |
| file.directURL | Direct URL to access the file with.                          |
| file.protected | true/false. Describes whether the file is protected or not.  |
