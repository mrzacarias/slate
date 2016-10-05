# Basic Authentication

* [Login](#login)
* [Logout](#logout)

#### Authenticated Requests

All API requests requiring authentication must have an authorization header with a valid API token.

Header:

````
Authorization: Token token="123456......abcdef"
````

-----

## Login

````
POST /api/v1/login
````

* email
* password

### Example Request

````
https://dev-portal-api.eyenetra.com:7443/api/v1/login
````

Parameters: you provide request parameters as JSON in your request's body

````
{
  "email":"user@eyenetra.com",
  "password":"password"
}
````

### Example Response

````
{
  "info": "Success",
  "token": "e6d21171662392915a6f093fb078ada6",
  "user": {
    "id": 1,
    "firstName": "user",
    "lastName": "user",
    "email": "user@eyenetra.com",
    "superAdmin": false,
    "canAdmin": false,
    "canPrescribe": false,
    "appointments": [],
    "locale": "en-US"
  },
  "organization": {
    "id": 1,
    "logo": "assets/images/eyenetra-brand.png",
    "prescribers": true,
    "plan": "professional",
    "created_at": "2016-06-20T19:51:40.064Z"
  }
}
````

-----

## Logout

````
DELETE /api/v1/logout
````

* token

### Example Request

````
https://dev-portal-api.eyenetra.com:7443/api/v1/logout
````

Header:

````
Authorization: Token token="123456......abcdef"
````

### Example Response

````
{
  "info": "Success"
}
````
