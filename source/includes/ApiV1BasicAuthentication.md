# Basic Authentication

All API requests requiring authentication must have an authorization header with a valid API token.

> Authorization Header

````
Authorization: Token token="123456......abcdef"
````

## Login

> Request Body

````
{
  "email":"user@eyenetra.com",
  "password":"password"
}
````

> Response Example 

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

The API Login uses email and password to generate a token. The request also returns the user and organization information.

### HTTP Request

`POST https://insight-api.eyenetra.com/api/v1/login`

### Body Parameters

Parameter       | Description
--------------- | -------------------------------------------------------------------------------
email           | The email used on the sign up
password        | Password (8 or more characters, at least 1 number)


## Logout

The API logout is a DELETE request. The API will use the token on the authorization header to do the log off logic. 

> Authorization Header

````
Authorization: Token token="123456......abcdef"
````

> Response Example 

````
{
  "info": "Success"
}
````

### HTTP Request

`DELETE https://insight-api.eyenetra.com/api/v1/logout`

### Body Parameters

None
