# Monocular

**Monoculars** are the test result structure responsible to keep the refraction data of a specific eye (Right or Left). Always associated with a Binocular structure.

#### Structure

* id
* eye
* sphere
* cylinder
* axis
* add
* va
* pd
* confidence

#### Authentication

All requests require [authentication](ApiV1BasicAuthentication).

-----

## Show

````
GET /api/v1/monoculars/{id}
````

### Example Request

````
https://dev-portal-api.eyenetra.com:7443/api/v1/monoculars/1
````

### Example Response

````
{
  "monocular": {
    "id": 1,
    "eye": "Right",
    "sphere": "-1.0",
    "cylinder": "-1.0",
    "axis": 1,
    "add": null,
    "va": "0.8",
    "pd": null,
    "confidence": null
  }
}
````
