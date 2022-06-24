---
description: >-
  This page covers the description of the type parameter inside
  GroupedAttributes enumeration
---

# Grouped Attibutes type

type paramter contains a pool of constants which determine the type of resulting data formed during the data scanning and processing cycle and passed to the user application.

```kotlin
class GroupedAttributes {
    companion object {
        val NONE = -1
        val DR_RESULT_TYPE_EMPTY = 0
        val DR_RESULT_TYPE_RAW_IMAGE = 1
        val DR_RESULT_TYPE_FILE_IMAGE = 2
        val DR_RESULT_TYPE_MRZ_OCR_EXTENDED = 3
        val DR_RESULT_TYPE_BARCODES = 5
        val DR_RESULT_TYPE_GRAPHICS = 6
        val DR_RESULT_TYPE_MRZ_TEST_QUALITY = 7
        val DR_RESULT_TYPE_DOCUMENT_TYPES_CANDIDATES = 8
        val DR_RESULT_TYPE_CHOSEN_DOCUMENT_TYPE_CANDIDATE = 9
        val DR_RESULT_TYPE_DOCUMENTS_INFO_LIST = 10
        val DR_RESULT_TYPE_OCR_LEXICAL_ANALYZE = 15
        val DR_RESULT_TYPE_RAW_UNCROPPED_IMAGE = 16
        val DR_RESULT_TYPE_VISUAL_OCR_EXTENDED = 17
        val DR_RESULT_TYPE_BAR_CODES_TEXT_DATA = 18
        val DR_RESULT_TYPE_BAR_CODES_IMAGE_DATA = 19
        val DR_RESULT_TYPE_AUTHENTICITY = 20
        val DR_RESULT_TYPE_EOS_IMAGE = 23
        val DR_RESULT_TYPE_BAYER_IMAGE = 24
        val DR_RESULT_TYPE_MAGNETIC_STRIPE = 25
        val DR_RESULT_TYPE_MAGNETIC_STRIPE_TEXT_DATA = 26
        val DR_RESULT_TYPE_FIELD_FILE_IMAGE = 27
        val DR_RESULT_TYPE_DATABASE_CHECK = 28
        val DR_RESULT_TYPE_FINGERPRINT_TEMPLATE_ISO = 29
        val DR_RESULT_TYPE_INPUT_IMAGE_QUALITY = 30
        val DR_RESULT_TYPE_IMAGES = 37
        val DR_RESULT_TYPE_HOLO_PARAMS = 47
        val DR_RESULT_TYPE_DOCUMENT_POSITION = 85
        val DR_RESULT_TYPE_CUSTOM = 100
        val RFID_RESULT_TYPE_RFID_RAW_DATA = 101
        val RFID_RESULT_TYPE_RFID_TEXT_DATA = 102
        val RFID_RESULT_TYPE_RFID_IMAGE_DATA = 103
        val RFID_RESULT_TYPE_RFID_BINARY_DATA = 104
        val RFID_RESULT_TYPE_RFID_ORIGINAL_GRAPHICS = 105
        val DR_RESULT_TYPE_BARCODE_POSITION = 62
        val DR_RESULT_TYPE_MRZ_POSITION = 61
    }
}
```



| Constant                                                | Description                                                                                                                                                                               |
| ------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **NONE**                                                | not identified                                                                                                                                                                            |
| **DR\_RESULT\_TYPE\_EMPTY**                             | no result                                                                                                                                                                                 |
| **DR\_RESULT\_TYPE\_RAW\_IMAGE**                        | stores a graphic image                                                                                                                                                                    |
| **DR\_RESULT\_TYPE\_FILE\_IMAGE**                       | represented as binary array which contains image of the image graphic file                                                                                                                |
| **DR\_RESULT\_TYPE\_MRZ\_OCR\_EXTENDED**                | serves for storing text results of MRZ, document filling and bar-codes reading                                                                                                            |
| **DR\_RESULT\_TYPE\_BARCODES**                          | serves for storing and passing to the user application of results of bar-codes areas search on the scanned document page and their reading in binary non-formatted code                   |
| **DR\_RESULT\_TYPE\_GRAPHICS**                          | serves for storing graphic results of document filling area and bar-codes reading                                                                                                         |
| **DR\_RESULT\_TYPE\_MRZ\_TEST\_QUALITY**                | serves for storing the information on document MRZ printing quality check results                                                                                                         |
| **DR\_RESULT\_TYPE\_DOCUMENT\_TYPES\_CANDIDATES**       | serves for storing information on candidate documents and passing it to the user application when performing the recognition of the document type                                         |
| **DR\_RESULT\_TYPE\_CHOSEN\_DOCUMENT\_TYPE\_CANDIDATE** | contains information on one candidate document when determining the document type                                                                                                         |
| **DR\_RESULT\_TYPE\_DOCUMENTS\_INFO\_LIST**             | not used. Serves for storing the full list of documents stored in the current document database and passing it to the user application                                                    |
| **DR\_RESULT\_TYPE\_OCR\_LEXICAL\_ANALYZE**             | serves for storing the results of comparing the MRZ text data, document filling area data, bar-codes data and data retrieved from RFID-chip memory and passing it to the user application |
| **DR\_RESULT\_TYPE\_RAW\_UNCROPPED\_IMAGE**             | result stores a graphic  image without compression                                                                                                                                        |
| **DR\_RESULT\_TYPE\_VISUAL\_OCR\_EXTENDED**             | result serves for storing text results of MRZ, document filling and bar-codes reading                                                                                                     |
| **DR\_RESULT\_TYPE\_BAR\_CODES\_TEXT\_DATA**            | result serves for storing text results of MRZ, document filling and bar-codes reading                                                                                                     |
| **DR\_RESULT\_TYPE\_BAR\_CODES\_IMAGE\_DATA**           | serves for storing graphic results of document filling area and bar-codes reading                                                                                                         |
| **DR\_RESULT\_TYPE\_AUTHENTICITY**                      | serves for storing the result of document authenticity check using the images for different lighting schemes and passing it to the user application                                       |
| **DR\_RESULT\_TYPE\_EOS\_IMAGE**                        | stores a graphic image in without compression and passing it to the user application                                                                                                      |
| **DR\_RESULT\_TYPE\_BAYER\_IMAGE**                      | stores a graphic image in without compression and passing it to the user application                                                                                                      |
| **DR\_RESULT\_TYPE\_MAGNETIC\_STRIPE**                  | represented as binary array which contains array if data erade from magnetic stripe                                                                                                       |
| **DR\_RESULT\_TYPE\_MAGNETIC\_STRIPE\_TEXT\_DATA**      | serves for storing text results of MRZ, document filling and bar-codes reading                                                                                                            |
| **DR\_RESULT\_TYPE\_FIELD\_FILE\_IMAGE**                | represented as binary array which contains image of the graphic field image graphic file                                                                                                  |
| **DR\_RESULT\_TYPE\_DATABASE\_CHECK**                   | serves for storing the result of documents database check                                                                                                                                 |
| **DR\_RESULT\_TYPE\_FINGERPRINT\_TEMPLATE\_ISO**        | represented as binary array which contains ISO fingerprint template                                                                                                                       |
| **DR\_RESULT\_TYPE\_INPUT\_IMAGE\_QUALITY**             | used for storing input image quality check results list                                                                                                                                   |
| **DR\_RESULT\_TYPE\_DOCUMENT\_POSITION**                | used for storing document bounds detection result                                                                                                                                         |
| **DR\_RESULT\_TYPE\_CUSTOM**                            | not used                                                                                                                                                                                  |
| **RFID\_RESULT\_TYPE\_RFID\_RAW\_DATA**                 | servers for storing the data reading results from the RFID-chip in a form of a list of the logically separated data groups                                                                |
| **RFID\_RESULT\_TYPE\_RFID\_TEXT\_DATA**                | servers for storing the results of data reading from the RFID-chip in a form of a list of logically separated text data (text fields)                                                     |
| **RFID\_RESULT\_TYPE\_RFID\_IMAGE\_DATA**               | servers for storing the results of data reading from the RFID- chip in a form of a list of logically separated graphic data (images, graphic fields)                                      |
| **RFID\_RESULT\_TYPE\_RFID\_BINARY\_DATA**              | servers for storing the data reading results from the RFID-chip in a form of a list of the logically separated data groups                                                                |
| **RFID\_RESULT\_TYPE\_RFID\_ORIGINAL\_GRAPHICS**        | servers for storing the results of data reading in a form of a list of objects of the original binary representation of the graphics in memory of the RFID-chip                           |
