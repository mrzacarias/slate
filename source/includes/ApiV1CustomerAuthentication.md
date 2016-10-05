# Customer Authentication

* [Customer Login](#customer-login)
* [Customer Logout](#customer-logout)

#### Authenticated Requests

Customer API requests requiring authentication must have an authorization header with a valid API token.

Header:

````
Authorization: Token token="123456......abcdef"
````

-----

## Customer Login

````
POST /api/v1/customer_login
````

* uuid - The UUID of a prescription in the database
* birthdate - The birthdate of the customer for whom that prescription applies.

### Example Request

````
https://dev-portal-api.eyenetra.com:7443/api/v1/customer_login
````

Parameters: you provide request parameters as JSON in your request's body

````
{
  "uuid":"00000000-0000-0000-0000-000000000000",
  "birthdate":"1950-01-01"
}
````

### Example Response

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

-----

## Customer Logout

````
DELETE /api/v1/customer_logout
````

* token

### Example Request

````
https://dev-portal-api.eyenetra.com:7443/api/v1/customer_logout
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
