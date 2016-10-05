# Users

* [List](#list)
* [Show](#show)
* [Create](#create)
* [Update](#update)
* [Delete](#delete)

**Users** can be created, updated, deleted and shown on the insight database. Each one can have or not a role and will belong to a single organization. ODs and Admins can administrate the users.

#### Structure
 * id
 * first_name
 * last_name
 * email
 * signature
 * title
 * license_number
 * license_state
 * npi
 * created_at
 * updated_at
 * role_ids

#### Authentication

All requests require [authentication](ApiV1BasicAuthentication).

------

## List

````
GET /api/v1/users
````

### Example Request

````
https://dev-portal-api.eyenetra.com:7443/api/v1/users
````

### Example Response

````
{
  "users": [
    {
      "id": 1,
      "first_name": "user",
      "last_name": "user",
      "email": "user@eyenetra.com",
      "signature": null,
      "title": null,
      "license_number": null,
      "license_state": null,
      "npi": null,
      "created_at": "2015-11-13T15:36:55.625Z",
      "role_ids": []
    },
    {
      "id": 2,
      "first_name": "admin",
      "last_name": "admin",
      "email": "admin@eyenetra.com",
      "signature": null,
      "title": "Admin",
      "license_number": null,
      "license_state": null,
      "npi": null,
      "created_at": "2015-11-13T15:36:55.724Z",
      "role_ids": [
        1
      ]
    }
  ]
}
````

### Filters

The following columns are available for filtering: 
* first_name
* last_name
* email
* signature
* title
* license_number
* license_state
* npi
* created_at
* updated_at

````
https://dev-portal-api.eyenetra.com:7443/api/v1/users?email=johndoe@email.com
````

### Searching

You can use the param "q" (for query) to set a string that will be used to search alike entries (case insensitive, using SQL "LIKE" command) on the following columns:
* first_name
* last_name
* email
* license_number
* license_state
* npi

````
https://dev-portal-api.eyenetra.com:7443/api/v1/users?q=John
````

### Sorting

The same columns used for filtering can be used for sorting. To sort your request, you pass the column name on the parameter "sort":

````
https://dev-portal-api.eyenetra.com:7443/api/v1/users?sort=npi
````

The default order when passing a parameter is ascending, you can change for descending passing a "-" before the column name:

````
https://dev-portal-api.eyenetra.com:7443/api/v1/users?sort=-npi
````

The default sort for requests is "-updated_at".

### "Since" parameters

You can also set "updated_since" or "created_since" parameters, specifying a bottom limit date or date/time to your requests

````
https://dev-portal-api.eyenetra.com:7443/api/v1/users?q=john&sort=-email&updated_since="01-01-2016"
````

------

## Show

````
GET /api/v1/users/{id}
````

### Example Request

````
https://dev-portal-api.eyenetra.com:7443/api/v1/users/2
````

### Example Response

````
{
  "user": {
    "id": 1,
    "first_name": "user",
    "last_name": "user",
    "email": "user@eyenetra.com",
    "signature": null,
    "title": null,
    "license_number": null,
    "license_state": null,
    "npi": null,
    "created_at": "2015-11-13T15:36:55.625Z",
    "role_ids": []
  }
}
````

------

## Create

````
POST /api/v1/users
````

### Example Request

````
{
  "user": {
    "first_name":"Rob",
    "last_name":"Park",
    "email":"rob@eyenetra.com",
    "password":"pass"
  }
}
````

### Example Response

````
{
  "user": {
    "id": 1,
    "first_name": "user",
    "last_name": "user",
    "email": "user@eyenetra.com",
    "signature": null,
    "title": null,
    "license_number": null,
    "license_state": null,
    "npi": null,
    "created_at": "2015-11-13T15:36:55.625Z",
    "role_ids": []
  }
}
````

------

## Update

````
PUT /api/v1/users/{id}
````

### Example Request

````
{
  "user":{
    "first_name":"Robert",
    "last_name":"Park",
    "email":"rob@eyenetra.com",
    "password":"pass"
  }
}
````

### Example Response

````
{
  "user": {
    "id": 1,
    "first_name": "user",
    "last_name": "user",
    "email": "user@eyenetra.com",
    "signature": null,
    "title": null,
    "license_number": null,
    "license_state": null,
    "npi": null,
    "created_at": "2015-11-13T15:36:55.625Z",
    "role_ids": []
  }
}
````

------

## Delete

````
DELETE /api/v1/users/{id}
````

### Example Request

````
https://dev-portal-api.eyenetra.com:7443/api/v1/users/2
````

### Example Response

````
{
  "info": "Success"
}
````
