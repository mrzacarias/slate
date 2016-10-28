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
Each appointment is related to one user ID and this user can get the list of his appointments by accessing the index request.

### Structure

The appointment object structure is optimized to work with [Full Calendar](https://fullcalendar.io/).

Field           | Description
--------------- | -------------------------------------------------------------------------------
id              | The object ID
title           | Short description/note to help to identify the appointment
start           | Date and Hour when the appointment will start
end             | Date and Hour when the appointment will end
user_id         | ID of the User associated with this element
visit_id        | ID of the Visit associated with this element
created_at      | When this object was created
updated_at      | Last time this objected was updated
organization_id | ID of the Organization associated with this element

<aside class="warn">
All requests require <a href="#basic-authentication">authentication</a>.
</aside>

## List

> Response Example 

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
There's no need to identify the user by passing an ID or something like that, the user will be identified by the auth token.

### HTTP Request

`GET https://insight-api.eyenetra.com/api/v1/appointments/`

### Query Parameters

None


## Show

> Response Example 

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

The show request will return the appointment for the ID passed as parameter.

### HTTP Request

`GET https://insight-api.eyenetra.com/api/v1/appointments/{id}`

### Query Parameters

Parameter       | Description
--------------- | -------------------------------------------------------------------------------
id              | The object ID
