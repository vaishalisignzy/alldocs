# Security

The online sandbox could be accessed without a separate security implementation. However for the Pre-Prod and Production environments, all API calls will be authenticated using key based mutual authentication

If you have completed integrating our APIs in your application you may start testing using the Pre-Prod environment.

Your Source IPs would be whitelisted in our Firewall. As per PCI Standards, all communications with Signzies APIs are allowed only through TLSv1.2 version. If your server still uses older versions of SSL/TLS you must upgrade to use our APIs.

The entire API payload would be encrypted end-to-end using the steps outlined in the Signzy Security framework document which will be shared to you.

In a nutshell, the payload originating from your end must be encrypted using a mix of our public key and vector, signed using your private key. Signzy Authentication engine would verify your signature using your public key and decrypt the payload using our private key. Inverse of this process would be followed for API response
