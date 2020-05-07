---
tags: [03. Error Codes]
---
# Error Codes
cubemos uses standard HTTP Response Codes to indicate the success or failure of a request. In general this means: 
* `2xx` - Everything went well. 
* `4xx` - Request failed but can be recovered programmatically. Details can retrieved from the actual HTTP response code and the returned error type. 
* `5xx` - Request failed due to an internal error on the cubemos server side. 

---

HTTP Response Code | Explanation
---------|----------
 200 - OK | Everything worked as expected 
 400 - Bad Request | Request was declined because of a client error. For example missing required parameters in the payload.  
 401 - Unauthorized | Thre request was declined because Authentication failed. Please see the [authentication docs](./02Authentication.md) if this happens to you.
 404 - Not found | The requested resource doesn't exist
 5xx  - Server Error | Something went wrong on our end. If this happens to you please contact [support@cubemos.com](mailto:support@cubemos.com)


 Error Type | Explanation
---------|----------
 A1 | B1 
 A2 | B2 
 A3 | B3 

