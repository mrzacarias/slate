# Instruments

> Instrument Structure Example

````
{
  "instrument": {
    "id": 1,
    "instrument_id": 406,
    "instrument_type": "Netra",
    "test_result_ids": ["..."],
    "created_at": "2016-06-20T20:02:35.687Z",
    "updated_at": "2016-06-20T20:02:35.687Z",
    "organization_id": 1
  }
}
````

**Instruments** are structures containing the organization devices information.
For EyeNetra devices, the information about each instrument (id, type, etc.) is saved/updated after
every new test result finished and uploaded.
Other non-EyeNetra devices will be saved as "custom" device, when a test result is created.

<aside class="warn">
All requests require <a href="#basic-authentication">authentication</a>.
</aside>

## List

> Response Example 

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

### HTTP Request

`GET https://insight-api.eyenetra.com/api/v1/instruments/`

## Show

> Response Example 

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

The basic show endpoint will return the instrument/device information for the Instrument ID passed on the request.

### HTTP Request

`GET https://insight-api.eyenetra.com/api/v1/instruments/{id}`
