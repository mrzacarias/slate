# Binocular

**Binoculars** are test results structures containing the binocular data (va, pd, etc.), as the two monoculars instances of customer right and left eyes.

#### Structure

* id
* pd
* va
* right eye id
* left eye id

#### Authentication

All requests require [authentication](ApiV1BasicAuthentication).

-----

## Show

````
GET /api/v1/binoculars/{id}
````

### Example Request

````
https://dev-portal-api.eyenetra.com:7443/api/v1/binoculars/1
````

### Example Response

````
{
  "binocular": {
    "id": 1,
    "pd": null,
    "va": "0.8",
    "right_eye_id": 1,
    "left_eye_id": 2
  },
  "monoculars": [...]
}
````
