---
tags: [02. Authentication]
---

# Authentication

Sanction List API from cubemos expects an API key to be included in all of its REST API calls. Without the key, the API request will fail with the error code 401. The key needs to be included in the header like so: 
<!-- theme: info -->
> ``` x-api-key: YOUR_API_KEY ```

The YOUR_API_KEY needs to be replaced with the key provided to you by cubemos. The key provided is used to manage your customer account in our backend and hence it is important that you keep it secret and not make it publically available. 

For the purpose of testing the API straight away from this documentation, you can use the following value for the key: 
<!-- theme: info -->
> ``` x-api-key: sanction_api_cubemos ```