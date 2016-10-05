# Appointments

* [List](#list)
* [Show](#show)

**Appointments** are structures containing the appointment data of visits scheduled by patients at the book visit page.

#### Structure

* id
* title
* start
* end
* user_id (OD related to the visit)
* visit_id

#### Authentication

All requests require [authentication](ApiV1BasicAuthentication).

-----

## List

````
GET /api/v1/appointments/
````

### Example Request

````
https://dev-portal-api.eyenetra.com:7443/api/v1/appointments/
````

### Example Response

````
{
  "appointments": [
    {
      "id": 40,
      "title": "test eyewear",
      "start": "2016-08-12T15:00:00.000Z",
      "end": "2016-08-12T16:00:00.000Z",
      "user_id": 2,
      "visit_id": 9762,
      "created_at": "2016-08-12T17:59:28.779Z",
      "updated_at": "2016-08-12T17:59:28.779Z",
      "organization_id": 1
    }
  ]
}
````

-----

## Show

````
GET /api/v1/appointments/{id}
````

### Example Request

````
https://dev-portal-api.eyenetra.com:7443/api/v1/appointments/40
````

### Example Response

````
{
  "appointment": {
    "id": 40,
    "title": "test eyewear",
    "start": "2016-08-12T15:00:00.000Z",
    "end": "2016-08-12T16:00:00.000Z",
    "user_id": 2,
    "visit_id": 9762,
    "created_at": "2016-08-12T17:59:28.779Z",
    "updated_at": "2016-08-12T17:59:28.779Z",
    "organization_id": 1
  }
}
````
