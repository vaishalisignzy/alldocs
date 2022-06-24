# Image Quality



You need to upload an image to detect the quality and decide whether it is usable for further processing. You may put direct URLs to images, in case you have them. To determine the quality of image we give a score out of 0-1, the model is trained on the basis of 4 types of distortions. This API can be used as an add-on to existing product to provide better user experience. The quality param(qualityParameter) in the request body is optional, by default it's value is all. The product has four types of quality checks namely:

* **Sharpness check** - This feature tells if the image is sharp i.e. no blur in image is present. 0 is blur, 1 is sharp. &#x20;
* **Brightness check** - This feature tells if the image is bright enough for OCR. 0 is dark, 1 is good bright.
* **Compression quality check** - This feature tells if the image is pixelated. 0 is compressed, 1 is good.
* **Text readable** - This tells whether the text present on the image is readable or not. 0 is bad, 1 is good.

<img src="https://docs-preproduction.signzy.tech/assets/images/image_quality_brightness.jpg" alt="" data-size="original">![](https://docs-preproduction.signzy.tech/assets/images/image\_quality\_blur.jpg)![](https://docs-preproduction.signzy.tech/assets/images/image\_quality\_compression.jpg)![](https://docs-preproduction.signzy.tech/assets/images/image\_quality\_text.jpg)

For best results, please make sure the image you use fits tightly in camera view and is horizontally-aligned.&#x20;

**Please note that each image should be less than 2MB. The API supports jpeg, png, and pdf formats.**

{% swagger baseUrl="https://preproduction.signzy.tech" path="/api/v2/patrons/….patron...id.../imagequality" method="post" summary="Image Quality" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="essenstials.colorAnalysisRequired" type="string" %}
whether color analysis to be done, allowed values: "true" / "false"
{% endswagger-parameter %}

{% swagger-parameter in="body" name="essentials.threshold" type="string" %}
threshold value between 0 and 1 for Accept/Reject. Default value will be 0.7. 
{% endswagger-parameter %}

{% swagger-parameter in="body" name="essentials.files" type="string" %}
URLs of the Image
{% endswagger-parameter %}

{% swagger-parameter in="body" name="essentials.qualityParameter" type="string" %}
"all" / "brightness" / "blur" / "compressionQuality" / "textQuality"
{% endswagger-parameter %}

{% swagger-parameter in="body" name="essentials" type="object" %}
Contains the essential input data
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "essentials": {
        "files": ["...url..to..file.." ],
        "qualityParameter": "all",
        "threshold": "Value between 0 and 1 to define accept/reject scenarios" 
    },
    "id": "5baXXXX",
    "patronId": "5a9XXXX",
    "result": {,
        "summary": "accept/reject/uncertain"
        "color": {
            "message": "message about the file.",
            "dominantColors": [
                "#colorCode",
                "#colorCode",
                ..
                ..
                ..
                "#colorCode"
            ]
        },
       "qualityScores": {
           "sharpness": {
               "score": "0 to 1",
               "valid": "yes | no"
           },
           "brightness": {
               "score": "0 to 1",
               "valid": "yes | no"
           },
           "compressionQuality": {
               "score": "0 to 1",
               "valid": "yes | no"
           },
           "textQuality": {
               "score": "0 to 1",
               "valid": "yes | no"
           }
       },
       "extractionQuality": "veryLow | low | medium | high",
       "score": "0 to 1",
       "msg": "done",
       "status": "200"
   }

} 
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="Request Schema" %}
```
{
  "essentials": {
    "files": ["...url..to..file.. (array of length one)"],
    "qualityParameter":"all",
    "threshold": "threshold value between 0 and 1 for Accept/Reject. Default value will be 0.7"
    "colorAnalysisRequired": "true/false"
  }
}
```
{% endtab %}

{% tab title="Response Parameters" %}
| PARAMETER NAME                   | Data Length | Data Type | DESCRIPTION                                                                                                                                                                                                                                                                              |
| -------------------------------- | ----------- | --------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| result                           | -           | object    | This holds the final response parameters.                                                                                                                                                                                                                                                |
| result.qualityScores             | -           | object    | This parameter assigns scores on the basis of overall image quality.                                                                                                                                                                                                                     |
| qualityScores.sharpness          | -           | object    | This parameter assigns scores based on the sharpness of the image.                                                                                                                                                                                                                       |
| sharpness.score                  | 3           | string    | This parameter returns a value between 0 and 1.                                                                                                                                                                                                                                          |
| sharpness.valid                  | 3           | string    | This parameter returns the validity as Yes/No.                                                                                                                                                                                                                                           |
| qualityScores.brightness         | -           | object    | This parameter assigns scores based on the brightness of the image.                                                                                                                                                                                                                      |
| brightness.score                 | 3           | string    | This parameter returns a value between 0 and 1.                                                                                                                                                                                                                                          |
| brightness.valid                 | 3           | string    | This parameter returns the validity as Yes/No.                                                                                                                                                                                                                                           |
| qualityScores.compressionQuality | -           | object    | This parameter assigns scores on the basis of compression quality of the image.                                                                                                                                                                                                          |
| compressionQuality.score         | 3           | string    | This parameter returns a value between 0 and 1.                                                                                                                                                                                                                                          |
| compressionQuality.valid         | 3           | string    | This parameter returns the validity as Yes/No.                                                                                                                                                                                                                                           |
| qualityScores.textQuality        | -           | object    | This parameter assigns scores on the basis of the quality of text on the image.                                                                                                                                                                                                          |
| textQuality.score                | 3           | string    | This parameter returns a value between 0 and 1.                                                                                                                                                                                                                                          |
| textQuality.valid                | 3           | string    | This parameter returns the validity as Yes/No.                                                                                                                                                                                                                                           |
| result.extractionQuality         | 10          | string    | This parameter determines the overall extraction quality of the image and returns one of the following - very Low/low/medium/high.                                                                                                                                                       |
| extractionQuality.score          | 3           | string    | This parameter returns a score between 0 to 1.                                                                                                                                                                                                                                           |
| extractionQuality.msg            | 100         | string    | This returns a status message.                                                                                                                                                                                                                                                           |
| extractionQuality.status         | 3           | string    | The status code is displayed here.                                                                                                                                                                                                                                                       |
| color.message                    | 100         | string    | Message about the file, black and white or not                                                                                                                                                                                                                                           |
| color.dominantColors             | -           | array     | Array of dominant colors                                                                                                                                                                                                                                                                 |
| result.summary                   | 10          | string    | accept/reject/uncertain. This value will depend on the threshold parameter. The parameter will be defined by the threshold value. It will be accept if the score is above the threshold, reject if the score is below the threshold and uncertain if the score could not be calculated.  |
{% endtab %}
{% endtabs %}
