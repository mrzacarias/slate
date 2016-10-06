# Organizations

**Organizations** are a logic division inside the Insight portal. All ODs, Admins and other users belongs to one and only organization and can make their actions only with elements (customers, visits, test results, etc.) related to this specific organization.

<aside class="warn">
All requests require <a href="#basic-authentication">authentication</a>.
</aside>

## List

### HTTP Request

`GET /api/v1/organizations`

> https://dev-portal-api.eyenetra.com:7443/api/v1/organizations

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

## Show

### HTTP Request

`GET /api/v1/organizations/{:organization_id}`

> https://dev-portal-api.eyenetra.com:7443/api/v1/organizations/1

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

## Create

### HTTP Request

`POST /api/v1/organizations/`

> https://dev-portal-api.eyenetra.com:7443/api/v1/organizations/1

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

## Update

### HTTP Request

`PUT /api/v1/organizations/{:organization_id}`

> https://dev-portal-api.eyenetra.com:7443/api/v1/organizations/1

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

## Delete

### HTTP Request

`DELETE /api/v1/organizations/{:organization_id}`

> https://dev-portal-api.eyenetra.com:7443/api/v1/organizations/1

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
