# Monocular

**Monoculars** are the test result structure responsible to keep the refraction data of a specific eye (Right or Left).
They are always associated with a Binocular structure.

> Example of a Monocular structure

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

### Structure

Field           | Description
--------------- | -------------------------------------------------------------------------------
id              | The Monocular object ID
eye             | Right or Left eye
sphere          | Sphere reading
cylinder        | Cylinder reading
axis            | Axis reading
add             | Add reading
va              | Monocular Visual Acuity
pd              | Monocular PD
confidence      | Confidence of this monocular

<aside class="warn">
All requests require <a href="#basic-authentication">authentication</a>.
</aside>

## Show

> Response Example 

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

This show endpoint will return the Monocular information correspondent to the id passed as parameter.

### HTTP Request

`GET https://insight-api.eyenetra.com/api/v1/monoculars/{id}`

### Query Parameters

Parameter       | Description
--------------- | -------------------------------------------------------------------------------
id              | The Monocular object ID
