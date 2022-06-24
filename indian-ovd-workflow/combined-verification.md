# Combined Verification

### Verifying Identity Card details

All details must be manually validated by the user before sending to the SIGNZY verification service. Upon receiving the details, they are cross-checked against government records to verify the authenticity of the details provided by the user.&#x20;

{% swagger baseUrl="https://preproduction.signzy.tech" path="/api/v2/snoops" method="post" summary="Identity Verification" %}
{% swagger-description %}
**Production URL:**

\




`https://signzy.tech/api/v2/snoops`

\




\


This method is used for verifying ID details by number and name or dob.
{% endswagger-description %}

{% swagger-parameter in="body" name="essentials" type="string" %}
Contains the details from the ID Card that need to be verified
{% endswagger-parameter %}

{% swagger-parameter in="body" name="accessToken" type="string" %}
identity access token
{% endswagger-parameter %}

{% swagger-parameter in="body" name="task" type="string" %}
Type of task performed - Verification
{% endswagger-parameter %}

{% swagger-parameter in="body" name="itemId" type="string" %}
identity item id
{% endswagger-parameter %}

{% swagger-parameter in="body" name="service" type="string" %}
type-identity
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
  "result": {
    "verified": true,
    "message": "Verification completed successfully"
  }
}
```
{% endswagger-response %}
{% endswagger %}

### PAN Verification

{% tabs %}
{% tab title="Request Schema PAN" %}
```
 {
      "service":"Identity",
      "itemId":"<Identity-object-id>",
      "task":"verification",
      "accessToken":"<Identity-access-token>",
      "essentials":{
        "number":"<PAN-as-mentioned-on-the-card>",
        "name":"<Name-corresponding-to-the-given-pan>",
        "fuzzy":"true/false"
        }
      }
```
{% endtab %}

{% tab title="Response Parameter PAN" %}
| PARAMETER NAME      | DESCRIPTION                                                                                |
| ------------------- | ------------------------------------------------------------------------------------------ |
| result              | The output of the response                                                                 |
| result.verified     | Contains the verification status "true/false"                                              |
| result.message      | This parameter displays the verification success/failure message to the user.              |
| result.upstreamName | This parameter checks the details of the PAN against the existing records in the database. |
{% endtab %}
{% endtabs %}

#### Verification Result Scenarios

1. Verification completed with positive result. - When PAN Number and Name perfectly matches with the Government recorded data.
2. Verification completed with negative result. - when PAN Number and Name does not match with the Government recorded data.
3. PAN not found.
   * The PAN Number is wrong.
   * The PAN Number is not found in our database.

### Driving Licence Verification

{% tabs %}
{% tab title="Request Schema Driving Licence" %}
```
{
  "service":"Identity",
  "itemId":"<Identity-id>",
  "task":"verification",
  "accessToken":"<Identity-access-token>",
  "essentials":{
    "number":"<Driving-Licence-Number>",
    "dob":"<Date of Birth>", // format dd/mm/yyyy
    "issueDate":"<Issue-Date>" // format dd/mm/yyyy
  }
}
```
{% endtab %}

{% tab title="Response Parameters Driving Licence" %}
| PARAMETER NAME  | DESCRIPTION                                                                   |
| --------------- | ----------------------------------------------------------------------------- |
| result          | The output of the response                                                    |
| result.verified | Contains the verification status "true/false"                                 |
| result.message  | This parameter displays the verification success/failure message to the user. |
{% endtab %}
{% endtabs %}

**Verification Result Scenarios**

* Driving licence verification process completed successfully with positive result - When DL Number and issue Date perfectly matches with the Government recorded data.
* &#x20;Driving licence verification process completed successfully with negative result. - when DL Number and issue Date doesn't match with the Government recorded data.
* The Provided DL Number is not found - This happens when:
  * The provided DL Number is wrong.
  * The provided DL Number is not updated in the government database.
  * Underlying government data source is having some issues at this moment.

The DL verification service is not applicable for licence issued in any one of the following states:&#x20;Bihar,  Jharkhand, Madhya Pradesh, West Bengal

### Passport Verification

{% tabs %}
{% tab title="Request Schema Passport" %}
```
{
      "service":"Identity",
      "itemId":"<Identity-object-id>",
      "task":"verification",
      "accessToken":"<Identity-access-token>",
      "essentials":{
            "fileNumber":"...fileNumber...",
            "dob":"...dob...",
            "name":"...name...",
            "fuzzy" : "true/false"
      }
}
```
{% endtab %}

{% tab title="Response Parameters Passport" %}
| PARAMETER NAME  | DESCRIPTION                                                                   |
| --------------- | ----------------------------------------------------------------------------- |
| result          | The output of the response                                                    |
| result.verified | Contains the verification status "true/false"                                 |
| result.message  | This parameter displays the verification success/failure message to the user. |
{% endtab %}
{% endtabs %}

****

###
