# Prescriptions

> Prescription Structure Example

````
{
  "prescription": {
    "id": 1,
    "left_sph": -1.25,
    "left_cyl": 0.4,
    "left_axis": 180,
    "left_add": -2,
    "right_sph": 1.25,
    "right_cyl": -0.5,
    "right_axis": 90,
    "right_add": 2.5,
    "pd": 65,
    "near_pd": 62,
    "recommended_use": "Near",
    "prescribing_od_id": 5
  }
}
````

If the OD decided to create a **Prescription**, an instance is created and saved on the database.

### Structure

Field             | Description
----------------- | -------------------------------------------------------------------------------
id                | The object ID
left_sph          | The left eye sphere reading
left_cyl          | The left eye cylinder reading
left_axis         | The left eye axis reading
left_add          | The left eye add reading
right_sph         | The right eye sphere reading
right_cyl         | The right eye cylinder reading
right_axis        | The right eye axis reading
right_add         | The right eye add reading
pd                | The prescription PD
near_pd           | The prescription Near PD
recommended_use   | Prescription user recommendation (Far, Near or Both)
prescribing_od_id | ID of the correspondent OD

<aside class="warn">
All requests require <a href="#basic-authentication">authentication</a>.
</aside>

## Show

> Response Example 

````
{
  "prescription": {
    "id": 1,
    "left_sph": -1.25,
    "left_cyl": 0.4,
    "left_axis": 180,
    "left_add": -2,
    "right_sph": 1.25,
    "right_cyl": -0.5,
    "right_axis": 90,
    "right_add": 2.5,
    "pd": 65,
    "near_pd": 62,
    "recommended_use": "Near",
    "prescribing_od_id": 5
  }
}
````

This show endpoint will return the Prescription information correspondent to the id passed as parameter.

### HTTP Request

`GET https://insight-api.eyenetra.com/api/v1/prescriptions/{:id}`


## Create

> Request Body

````
{
  "left_sph":"0.25",
  "recommended_use":"Near",
  "note":"How many fingers am I holding up?",
  "visit_id":221
}
````

> Response Example 

````
{
  "prescription":    
    {
      "id": 1,
      "left_sph": -1.25,
      "left_cyl": 0.4,
      "left_axis": 180,
      "left_add": -2,
      "right_sph": 1.25,
      "right_cyl": -0.5,
      "right_axis": 90,
      "right_add": 2.5,
      "pd": 65,
      "near_pd": 62,
      "recommended_use": "Near",
      "prescribing_od_id": 5
    }
}
````

If the prescription information is right, a new prescription will be created and the information will be available
on the response body.

### HTTP Request

`POST https://insight-api.eyenetra.com/api/v1/prescriptions`


## Update

> Request Body

````
{
  "left_sph":"0.25",
  "recommended_use":"Near",
  "note":"How many fingers am I holding up?",
  "visit_id":221
}
````

> Response Example 

````
{
  "prescription":    
    {
      "id": 1,
      "left_sph": -1.25,
      "left_cyl": 0.4,
      "left_axis": 180,
      "left_add": -2,
      "right_sph": 1.25,
      "right_cyl": -0.5,
      "right_axis": 90,
      "right_add": 2.5,
      "pd": 65,
      "near_pd": 62,
      "recommended_use": "Near",
      "prescribing_od_id": 5
    }
}
````

Basic update endpoint, will update the target prescription if the request body information is right.

### HTTP Request

`PUT https://insight-api.eyenetra.com/api/v1/prescriptions`
