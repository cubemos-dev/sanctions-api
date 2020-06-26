---
tags: [02. Quickstart]
---

# Quick start

If you want to check out the possibilities of the cubemos sanction list api, you can test the individual endpoints of the api in the "Try it" sections. 

For a start, let's try to check if a specific person (in this case Serhii Kliuiev) is under sanctions. 

In order to do so we will

- make a request to the [/search/entities/person](../swagger/sanctions_list.v1.yaml/paths/~1search~1location~1address/post) endpoint.
- use the result to get first-hand information from an official sanction list.

### Make a search request

You can trigger the api by clicking `send`on the the element below.

```json http
{
  "method": "post",
  "url": "https://api.cubemos.com/sanction/search/entities/person",
  "headers": {
    "Content-Type": "application/json",
    "x-api-key": "cubemos_sanction_api"
  },
  "body": {
    "search_config": {
      "sanction_lists": [
        "cfsp",
        "SDN"
      ],
      "must_match_attributes": [
        "full_name"
      ]
    },
    "person": {
      "full_name": "OCHOA VASCO, Fabio Enrique",
      "first_name": "",
      "middle_name": "",
      "last_name": "",
      "aliases": [
        "Mario"
      ],
      "gender": "",
      "dob": "",
      "city": "",
      "nationality": ""
    }
  }
}
```

### Investigate opposed sanctions

If you investigate the response of the request above, you can see that indeed, there is a person under sanctions which matches the name. For further inspection you can now use the id of `list_entry_url` in the request below to see the details of the opposed sanctions.

```json http
{
  "method": "get",
  "url": "https://api.cubemos.com/sanction/list/sdn/10133",
   "headers": {
    "x-api-key": "cubemos_sanction_api"
  }
}
```

### Workflow

1. Get your personal API Key from cubemos. 
2. Make a POST request to search for sanctions opposed to a [person](../swagger/sanctions_list.v1.yaml/paths/~1search~1entities~1person/post), an [address](../swagger/sanctions_list.v1.yaml/paths/~1search~1location~1address/post) or an [organization](../swagger/sanctions_list.v1.yaml/paths/~1search~1entities~1organization/post)
