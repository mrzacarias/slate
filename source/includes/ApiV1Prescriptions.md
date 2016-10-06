# Prescriptions

If the OD decided to create a **Prescription**, an instance is created and saved on the database. Is also possible for the OD to update the visit.

#### Structure

 * id
 * left_sph
 * left_cyl
 * left_axis
 * left_add
 * right_sph
 * right_cyl
 * right_axis
 * right_add
 * pd
 * near_pd
 * recommended_use
 * prescribing_od_id

<aside class="warn">
All requests require <a href="#basic-authentication">authentication</a>.
</aside>

## Show

### HTTP Request

`GET /api/v1/prescriptions/{:id}`

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

## Create

### HTTP Request

`POST /api/v1/prescriptions`

> https://dev-portal-api.eyenetra.com:7443/api/v1/prescriptions

````
{
  "left_sph":"0.25",
  "recommended_use":"Near",
  "note":"How many fingers am I holding up?",
  "visit_id":221
}
````

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

## Update

### HTTP Request

`PUT /api/v1/prescriptions`

> https://dev-portal-api.eyenetra.com:7443/api/v1/prescriptions

````
{
  "left_sph":"0.25",
  "recommended_use":"Near",
  "note":"How many fingers am I holding up?",
  "visit_id":221
}
````

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
