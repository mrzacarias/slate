# Instruments

**Instruments** are structures containing the organization devices information. For EyeNetra devices, the information about each instrument (id, type, etc.) is saved/updated after every new test result finished and uploaded.

#### Structure

* id
* instrument_id
* instrument_type
* test_result_ids

<aside class="warn">
All requests require <a href="#basic-authentication">authentication</a>.
</aside>

## List

### HTTP Request

`GET /api/v1/instruments/`

> https://dev-portal-api.eyenetra.com:7443/api/v1/instruments/

````
{
  "instruments": [
    {
      "id": 8,
      "instrument_id": -1,
      "instrument_type": "Netra",
      "organization_id": 1,
      "test_result_ids": ["..."],
      "created_at": "2016-06-20T22:06:56.899Z",
      "updated_at": "2016-06-20T22:06:56.899Z"
    },
    {
      "id": 1,
      "instrument_id": 406,
      "instrument_type": "Netra",
      "organization_id": 1,
      "test_result_ids": ["..."],
      "created_at": "2016-06-20T20:02:35.687Z",
      "updated_at": "2016-06-20T20:02:35.687Z"
    }
  ]
}
````

## Show

### HTTP Request

`GET /api/v1/instruments/{id}`

> https://dev-portal-api.eyenetra.com:7443/api/v1/instruments/1

````
{
  "instrument": {
    "id": 1,
    "instrument_id": 406,
    "instrument_type": "Netra",
    "organization_id": 1,
    "test_result_ids": ["..."],
    "created_at": "2016-06-20T20:02:35.687Z",
    "updated_at": "2016-06-20T20:02:35.687Z"
  }
}
````
