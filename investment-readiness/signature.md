# Signature

You can collect signature from the Investor in two ways. The first way is to give the option to the Investor to sign on a blank paper with a pen and upload the signature file. The second way is to give the option to the Investor to sign digitally on the mobile application screen. We call it "Normal E-Sign". You can use either of the APIs to collect, verify, and share the signature with us.

## Upload Signature

{% swagger method="post" path="/upload_signature" baseUrl="https://<<BASE URL>>/investment_readiness" summary="Upload the signature of the Investor." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="signature" type="File" required="true" %}

{% endswagger-parameter %}

{% swagger-response status="201: Created" description="Success" %}
```javascript
{
    "status": "success",
    "message": "Signature uploaded successfully",
    "wayneReferenceId": "***********"
}
```
{% endswagger-response %}
{% endswagger %}

## Normal E-Sign

{% swagger method="post" path="/normal_esign" baseUrl="https://<<BASE URL>>/investment_readiness" summary="You will be able to let the Investor do a normal e-sign using this API endpoint." %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" required="true" name="signature" type="File" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "status": "success",
    "message": "Normal e-sign successfully submitted",
    "wayneReferenceId": "**************"
}
```
{% endswagger-response %}
{% endswagger %}
