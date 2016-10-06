# Binocular

**Binoculars** are test results structures containing the binocular data (va, pd, etc.), as the two monoculars instances of customer right and left eyes.

> Example of a Binocular structure

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

### Structure

Field           | Description
--------------- | -------------------------------------------------------------------------------
id              | The Binocular object ID
pd              | Binocular PD
va              | Binocular Visual Acuity
right_eye_id    | Right Eye Monocular ID
left_eye_id     | Left Eye Monocular ID
monoculars      | List of monoculars associated with this binocular

<aside class="warn">
All requests require <a href="#basic-authentication">authentication</a>.
</aside>

## Show

> https://dev-portal-api.eyenetra.com:7443/api/v1/binoculars/1

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

### HTTP Request

`GET /api/v1/binoculars/{id}`

### Query Parameters

Parameter       | Description
--------------- | -------------------------------------------------------------------------------
id              | The Binocular object ID
