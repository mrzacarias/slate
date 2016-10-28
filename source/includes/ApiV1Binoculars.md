# Binocular

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
  "monoculars": ["..."]
}
````

**Binoculars** are test results structures containing both eyes refraction information.
Each binocular object contains the binocular information (pd, visual acuity for both eyes, etc.) and 
also contains two monoculars objects, one for right eye and other for left eye.

Se more about the monocular structure at the [correspondent section](#monocular) on this documentation.

### Structure

Field           | Description
--------------- | -------------------------------------------------------------------------------
id              | The object ID
pd              | Binocular PD
va              | Binocular Visual Acuity
right_eye_id    | Right Eye Monocular ID
left_eye_id     | Left Eye Monocular ID
monoculars      | List of monoculars associated with this binocular

<aside class="warn">
All requests require <a href="#basic-authentication">authentication</a>.
</aside>

## Show

> Response Example 

````
{
  "binocular": {
    "id": 1,
    "pd": null,
    "va": "0.8",
    "right_eye_id": 1,
    "left_eye_id": 2
  },
  "monoculars": ["..."]
}
````

You can get a specfic binocular information by passing the binocular ID to the show request.
The object will be returned with the binocular information and also the right and left eyes monocular 
information, sideloaded on the response body.

### HTTP Request

`GET https://insight-api.eyenetra.com/api/v1/binoculars/{id}`

### Query Parameters

Parameter       | Description
--------------- | -------------------------------------------------------------------------------
id              | The Binocular object ID
