---
tags: [04. Quickstart]
---

# Quickstart

## For Non-Developers

If you want to check out the possibilities of the cubemos sanction list api, you can test the individual endpoints of the api in the "Try it" sections. 

For a start, let's try to check if a specific person is under sanctions by making a request to the [/search/entities/person](<>) endpoint.

```json http
{
  "method": "post",
  "url": "https://sanctions-api.cubemos.com/v1/search/entities/person",
  "headers": {
    "Content-Type": "application/json"
  }
}
```

## For Developers
