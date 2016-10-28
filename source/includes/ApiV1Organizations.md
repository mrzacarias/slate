# Organizations

**Organizations** are a logic group inside the Insight portal.
All ODs, Admins and other users belongs to one and only organization and can make their actions only
with elements (customers, visits, test results, etc.) related to this specific organization.

<aside class="warn">
All requests require <a href="#basic-authentication">authentication</a>.
</aside>

## List

> Response Example 

````
{
  "organizations": [
    {
      "id": 2,
      "name": "blonk",
      "kind": "single_OD",
      "logo": "GoBlonk.png",
      "template": "blonk"
    },
    {
      "id": 3,
      "name": "generic",
      "kind": "single_OD",
      "logo": null,
      "template": "generic"
    },
    {
      "id": 1,
      "name": "blink",
      "kind": "multiple_ODs_with_visioneers",
      "logo": "GoBlink.png",
      "template": "blink"
    }
  ]
}
````

This endpoint will return the list of Insight organizations, only for Super Admins.

### HTTP Request

`GET https://insight-api.eyenetra.com/api/v1/organizations`


## Show

> Response Example 

````
{
  "organization": {
    "id": 1,
    "name": "blink",
    "kind": "multiple_ODs_with_visioneers",
    "logo": "GoBlink.png",
    "template": "blink"
  }
}
````

This show endpoint will return the Organization information correspondent to the id passed as parameter.

### HTTP Request

`GET https://insight-api.eyenetra.com/api/v1/organizations/{:organization_id}`


## Create

> Request Body

````
{
  "organization": {
    "name":"blink"
  }
}
````

> Response Example 

````
{
  "organization": {
    "id": 1,
    "name": "blink",
    "kind": "multiple_ODs_with_visioneers",
    "logo": "GoBlink.png",
    "template": "blink"
  }
}
````

The create endpoint will create a new organization if the correct information is passed.

### HTTP Request

`POST https://insight-api.eyenetra.com/api/v1/organizations/`


## Update

> Response Example 

````
{
  "organization": {
    "id": 1,
    "name": "blink",
    "kind": "multiple_ODs_with_visioneers",
    "logo": "GoBlink.png",
    "template": "blink"
  }
}
````

This update endpoint will update the target organization information.

### HTTP Request

`PUT https://insight-api.eyenetra.com/api/v1/organizations/{:organization_id}`
