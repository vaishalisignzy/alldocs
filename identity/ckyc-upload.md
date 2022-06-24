# CKYC upload

Following details need to be uploaded via CKYC API. Details of each field:

| NAME                      | TYPE    | LENGTH | REMARKS                                                                                  |
| ------------------------- | ------- | ------ | ---------------------------------------------------------------------------------------- |
| Client Code               | Varchar | 10     |                                                                                          |
| Client PAN                | Varchar | 10     | Mandatory if Tax Status is not 02 (Should Match with Existing PAN Given for Client Code) |
| First Holder CKYC Number  | Numeric | 14     |                                                                                          |
| Second Holder CKYC Number | Numeric | 14     |                                                                                          |
| Third Holder CKYC Number  | Numeric | 14     |                                                                                          |
| Guardian CKYC Number      | Numeric | 14     |                                                                                          |
| Joint Holder 1 DOB        | DATE    | 10     | DD/MM/YYYY                                                                               |
| Joint Holder 2 DOB        | DATE    | 10     | DD/MM/YYYY                                                                               |
| Guardian CKYC DOB         | DATE    | 10     | DD/MM/YYYY                                                                               |
| KYC\_Type\_First Holder   | CHAR    | 1      | (K/C) (K - KRA Compliant C- CKYC Compliant)                                              |
| KYC\_Type\_Second Holder  | CHAR    | 1      | (K/C) (K - KRA Compliant C- CKYC Compliant)                                              |
| KYC\_Type\_Third Holder   | CHAR    | 1      | (K/C) (K - KRA Compliant C- CKYC Compliant)                                              |
| KYC\_Type\_Guardian       | CHAR    | 1      | (K/C) (K - KRA Compliant C- CKYC Compliant)                                              |

{% swagger method="get" path="" baseUrl="" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="client_code" type="Varchar" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="clent_PAN" type="Varchar" required="true" %}
Mandatory if Tax Status is not 02 (Should Match with Existing PAN Given for Client Code)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="first_holder_CKYC_number" type="Numeric" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="first_holder_CKYC_number" type="Numeric" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="first_holder_CKYC_number" type="Numeric" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="guardian_CKYC_number" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="joint_holder_1_DOB" type="Date" %}
DD/MM/YYYY
{% endswagger-parameter %}

{% swagger-parameter in="body" name="joint_holder_2_DOB" type="Date" %}
DD/MM/YYYY
{% endswagger-parameter %}

{% swagger-parameter in="body" name="guardian_CKYC_DOB" type="Date" %}
DD/MM/YYYY
{% endswagger-parameter %}

{% swagger-parameter in="body" name="KYC_type_first_holder" type="CHAR" %}
(K/C) (K - KRA Compliant C- CKYC Compliant)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="KYC_type_second_holder" type="CHAR" %}
(K/C) (K - KRA Compliant C- CKYC Compliant)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="KYC_type_third_holder" type="CHAR" %}
(K/C) (K - KRA Compliant C- CKYC Compliant)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="KYC_type_guardian" type="CHAR" %}
(K/C) (K - KRA Compliant C- CKYC Compliant)
{% endswagger-parameter %}
{% endswagger %}

