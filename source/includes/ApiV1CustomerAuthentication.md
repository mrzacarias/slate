# Customer Authentication

Customer API requests requiring authentication must have an authorization header with a valid API token.

> Authorization Header

````
Authorization: Token token="123456......abcdef"
````

## Customer Login

> Request Body

````
{
  "uuid":"00000000-0000-0000-0000-000000000000",
  "birthdate":"1950-01-01"
}
````

> Response Example 

````
{
  "info": "Success",
  "token": "123456......abcdef",
  "user": {
    "firstName": "Ammo"
  },
  "organization": {
    "id": 1,
    "logo": "assets/images/eyenetra-brand.png"
  }
}
````

The API Login uses the visit uuid and the customer birthdate to generate a token. The request also returns the customer and organization information.

### HTTP Request

`POST /api/v1/customer_login`

### Body Parameters

Parameter       | Description
--------------- | -------------------------------------------------------------------------------
uuid            | The UUID of a prescription in the database
birthdate       | The birthdate of the customer for whom that prescription applies.


## Customer Logout

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

`DELETE /api/v1/customer_logout`

### Body Parameters

None
