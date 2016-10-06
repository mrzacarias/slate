# Users

> User Structure Example

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

**Users** can be created, updated, deleted and shown on the insight database. Each one can have or not a role and will belong to a single organization. ODs and Admins can administrate the users.

### Structure

Field             | Description
----------------- | -------------------------------------------------------------------------------
id                | The object ID
first_name        | TODO
last_name         | TODO
email             | TODO
signature         | TODO
title             | TODO
license_number    | TODO
license_state     | TODO
npi               | TODO
created_at        | TODO
updated_at        | TODO
role_ids          | TODO

<aside class="warn">
All requests require <a href="#basic-authentication">authentication</a>.
</aside>

## List

> https://dev-portal-api.eyenetra.com:7443/api/v1/users

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

### HTTP Request

`GET /api/v1/users`

## Filtering, Searching and Sorting

### Filters

> https://dev-portal-api.eyenetra.com:7443/api/v1/users?email=johndoe@email.com

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

### Searching

> https://dev-portal-api.eyenetra.com:7443/api/v1/users?q=John

You can use the param "q" (for query) to set a string that will be used to search alike entries (case insensitive, using SQL "LIKE" command) on the following columns:
* first_name
* last_name
* email
* license_number
* license_state
* npi

### Sorting

> https://dev-portal-api.eyenetra.com:7443/api/v1/users?sort=npi

The same columns used for filtering can be used for sorting. To sort your request, you pass the column name on the parameter "sort":

> https://dev-portal-api.eyenetra.com:7443/api/v1/users?sort=-npi

The default order when passing a parameter is ascending, you can change for descending passing a "-" before the column name:

The default sort for requests is "-updated_at".

### "Since" parameters

> https://dev-portal-api.eyenetra.com:7443/api/v1/users?q=john&sort=-email&updated_since="01-01-2016"

You can also set "updated_since" or "created_since" parameters, specifying a bottom limit date or date/time to your requests

## Show

> https://dev-portal-api.eyenetra.com:7443/api/v1/users/2

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

### HTTP Request

`GET /api/v1/users/{id}`


## Create

> Request Body

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

> https://dev-portal-api.eyenetra.com:7443/api/v1/users/

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
### HTTP Request

`POST /api/v1/users`


## Update


> Request Body

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

> https://dev-portal-api.eyenetra.com:7443/api/v1/users/

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

### HTTP Request

`PUT /api/v1/users/{id}`


## Delete

> https://dev-portal-api.eyenetra.com:7443/api/v1/users/2

````
{
  "info": "Success"
}
````

### HTTP Request

`DELETE /api/v1/users/{id}`
