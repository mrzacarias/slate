# Organizations

* [List](#list)
* [Show](#show)
* [Create](#create)
* [Update](#update)
* [Delete](#delete)

**Organizations** are a logic division inside the Insight portal. All ODs, Admins and other users belongs to one and only organization and can make their actions only with elements (customers, visits, test results, etc.) related to this specific organization.

#### Authentication

All requests require [authentication](ApiV1BasicAuthentication).

-----

## List

````
GET /api/v1/organizations
````

### Example Request

````
https://dev-portal-api.eyenetra.com:7443/api/v1/organizations
````

### Example Response

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

-----

## Show

````
GET /api/v1/organizations/{:organization_id}
````

### Example Request

````
https://dev-portal-api.eyenetra.com:7443/api/v1/organizations/1
````

### Example Response

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

-----

## Create

````
POST /api/v1/organizations/
````

### Example Request

````
https://dev-portal-api.eyenetra.com:7443/api/v1/organizations/1

payload
````

### Example Response

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

-----

## Update

````
PUT /api/v1/organizations/{:organization_id}
````

### Example Request

````
https://dev-portal-api.eyenetra.com:7443/api/v1/organizations/1

payload
````

### Example Response

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


-----

## Delete

````
GET /api/v1/organizations/{:organization_id}
````

### Example Request

````
https://dev-portal-api.eyenetra.com:7443/api/v1/organizations/1
````

### Example Response

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
