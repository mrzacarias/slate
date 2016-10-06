# Appointments

> Example of a Appointment structure

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

**Appointments** are structures containing the appointment data of visits scheduled by patients at the book visit page.

### Structure

Field           | Description
--------------- | -------------------------------------------------------------------------------
id              | The Appointment object ID
title           | Short description/note to help to identify the appointment
start           | Date and Hour when the appointment will start
end             | Date and Hour when the appointment will end
user_id         | ID of the User associated with this element
visit_id        | ID of the Visit associated with this element
created_at      | When this object was created
updated_at      | Last time this objected was updated
organization_id | ID of the Organization associated with this element

<aside class="success">
All requests require <a href="#basic-authentication">authentication</a>.
</aside>

## List

> https://dev-portal-api.eyenetra.com:7443/api/v1/appointments/

````
{
  "appointments": [
    {
      "id": 40,
      "title": "test",
      "start": "2016-08-12T15:00:00.000Z",
      "end": "2016-08-12T16:00:00.000Z",
      "user_id": 2,
      "visit_id": 9762,
      "created_at": "2016-08-12T17:59:28.779Z",
      "updated_at": "2016-08-12T17:59:28.779Z",
      "organization_id": 1
    },
    {
      "id": 42,
      "title": "another test",
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

The List request will return all the appointments of the current user.

### HTTP Request

`GET /api/v1/appointments/`

### Query Parameters

None


## Show

The show request will return the appointment for the ID passed as parameter.

> https://dev-portal-api.eyenetra.com:7443/api/v1/appointments/40

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
### HTTP Request

`GET /api/v1/appointments/{id}`

### Query Parameters

Parameter       | Description
--------------- | -------------------------------------------------------------------------------
id              | The Appointment object ID
