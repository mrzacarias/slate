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

If the OD decided to create a **Prescription**, an instance is created and saved on the database. Is also possible for the OD to update the visit.

### Structure

Field             | Description
----------------- | -------------------------------------------------------------------------------
id                | The object ID
left_sph          |  TODO
left_cyl          | TODO
left_axis         | TODO
left_add          | TODO
right_sph         | TODO
right_cyl         | TODO
right_axis        | TODO
right_add         | TODO
pd                | TODO
near_pd           | TODO
recommended_use   | TODO
prescribing_od_id | TODO

<aside class="warn">
All requests require <a href="#basic-authentication">authentication</a>.
</aside>

## Show

> https://dev-portal-api.eyenetra.com:7443/api/v1/prescriptions/1

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

### HTTP Request

`GET /api/v1/prescriptions/{:id}`

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

> https://dev-portal-api.eyenetra.com:7443/api/v1/prescriptions

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

### HTTP Request

`POST /api/v1/prescriptions`

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

> https://dev-portal-api.eyenetra.com:7443/api/v1/prescriptions

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

### HTTP Request

`PUT /api/v1/prescriptions`
