---
description: General Errors
---

# Errors

Our API returns standard HTTP success or error status codes. For errors, we will also include extra information about what went wrong in the message field in the response as JSON. The various HTTP status codes that might be returned are listed below.

| Code | Title                             | Description                                                                                                                                                                                          |
| ---- | --------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 200  | OK                                | The request was successful.                                                                                                                                                                          |
| 204  | Not Modified                      | There was no new data to return.                                                                                                                                                                     |
| 400  | Bad Request                       | The request was invalid or cannot be otherwise served. This may happen due to invalid Parameters passed.                                                                                             |
| 401  | Authorization Required            | Missing or incorrect authentication credentials.                                                                                                                                                     |
| 403  | Access Forbidden                  | The request is understood, but it has been refused or access is not allowed. An accompanying error message will explain why. This code is used when requests are being denied due to request limits. |
| 404  | Not Found                         | The URI requested is invalid or the resource requested is not available.                                                                                                                             |
| 422  | Un-processable Entity             | Missing Inputs or the JSON body of a request is badly-formed.                                                                                                                                        |
| 500  | Internal Server Error             | Something is broken. This is usually a temporary error, for example in a high load situation or if an endpoint is temporarily having issues.Try again later.                                         |
| 502  | Bad gateway/Internal Server Error | Signzy service is down or the service is getting upgraded.                                                                                                                                           |
| 504  | Gateway Timeout                   | The Signzy servers are up, but the request couldn’t be serviced due to some failure within the internal stack. Try again later.                                                                      |
