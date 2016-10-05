# Instruments

**Instruments** are structures containing the organization devices information. For EyeNetra devices, the information about each instrument (id, type, etc.) is saved/updated after every new test result finished and uploaded.

#### Structure

* id
* instrument_id
* instrument_type
* test_result_ids

#### Authentication

All requests require [authentication](ApiV1BasicAuthentication).

-----

## List

````
GET /api/v1/instruments/
````

### Example Request

````
https://dev-portal-api.eyenetra.com:7443/api/v1/instruments/
````

### Example Response

````
{
  "instruments": [
    {
      "id": 8,
      "instrument_id": -1,
      "instrument_type": "Netra",
      "organization_id": 1,
      "test_result_ids": [...],
      "created_at": "2016-06-20T22:06:56.899Z",
      "updated_at": "2016-06-20T22:06:56.899Z"
    },
    {
      "id": 1,
      "instrument_id": 406,
      "instrument_type": "Netra",
      "organization_id": 1,
      "test_result_ids": [...],
      "created_at": "2016-06-20T20:02:35.687Z",
      "updated_at": "2016-06-20T20:02:35.687Z"
    }
  ]
}
````

-----

## Show

````
GET /api/v1/instruments/{id}
````

### Example Request

````
https://dev-portal-api.eyenetra.com:7443/api/v1/instruments/1
````

### Example Response

````
{
  "instrument": {
    "id": 1,
    "instrument_id": 406,
    "instrument_type": "Netra",
    "organization_id": 1,
    "test_result_ids": [...],
    "created_at": "2016-06-20T20:02:35.687Z",
    "updated_at": "2016-06-20T20:02:35.687Z"
  }
}
````
