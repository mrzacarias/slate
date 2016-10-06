# Organizations

**Organizations** are a logic division inside the Insight portal. All ODs, Admins and other users belongs to one and only organization and can make their actions only with elements (customers, visits, test results, etc.) related to this specific organization.

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

### HTTP Request

`GET /api/v1/organizations`

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

### HTTP Request

`GET /api/v1/organizations/{:organization_id}`

## Create

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

### HTTP Request

`POST /api/v1/organizations/`

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

### HTTP Request

`PUT /api/v1/organizations/{:organization_id}`
