---
tags: [01. API reference]
---

# API reference

The cubemos Sanction List API is a RESTful API which can be used to ensure compliance with relevant regulations across the globe. Visit the [overview](../swagger/sanctions_list.v1.yaml) page to get to know the possibilities in detail.

---

### Quick start

Check for sanctionized person or organization based on their attributes or get all the sanctionized entities at an address using the following POST calls: 
1. [/search/entities/person](../swagger/sanctions_list.v1.yaml/paths/~1search~1entities~1person/post) 
2. [search/entities/organization](../swagger/sanctions_list.v1.yaml/paths/~1search~1entities~1organization/post) 
3. [search/location/address](../swagger/sanctions_list.v1.yaml/paths/~1search~1location~1address/post)

Review the original sanction list entries for the sanctionized person using the following GET calls:

4. [/list/cfsp/{id}](../swagger/sanctions_list.v1.yaml/paths/~1list~1cfsp~1{id}/get)
5. [/list/ofac-sdn/{id}](../swagger/sanctions_list.v1.yaml/paths/~1list~1ofac-sdn~1{id}/get)
5. [/list/ofac-csl/{id}](../swagger/sanctions_list.v1.yaml/paths/~1list~1ofac-csl~1{id}/get)
5. [/list/hm-treasury/{id}](../swagger/sanctions_list.v1.yaml/paths/~1list~1hm-treasury~1{id}/get)

<!-- theme: warning -->
> Please enter "sanction_api_cubemos" as the x-api-key in the "Try-it out" section of each call in order to execute them and get the results for each example

---
#### **Investigate a sanctionized person**

###### 1. Check if the person is black-listed
Test it right now by clicking on `send` button.

```json http
{
  "method": "post",
  "url": "https://api.cubemos.com/sanction/search/entities/person",
  "headers": {
    "Content-Type": "application/json",
    "x-api-key": "sanction_api_cubemos"
  },
  "body": {
    "search_config": {
      "sanction_lists": [
        "cfsp",
        "ofac_sdn"
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

###### 2. In case the person was found, review the original sanction list entry
Retrieve the full original entry based on the ID of the `list_entry_url` of the above POST request.

```json http
{
  "method": "get",
  "url": "https://api.cubemos.com/sanction/list/ofac-sdn/10214",
   "headers": {
    "x-api-key": "sanction_api_cubemos"
  }
}
```



