# Tablet Authentication

* [Tablet Login](#tablet-login)
* [Tablet Logout](#tablet-logout)

#### Authenticated Requests

Tablet API requests requiring authentication must have an authorization header with a valid API token.

Header:

````
Authorization: Token token="123456......abcdef"
````

-----

## Tablet Login

````
POST /api/v1/tablet_login
````

* email
* password


If credentials aren't valid, the API will return a 401: Unauthorized.

* email: un@known.com
* password: password 

If credentials are valid but Visioneer role not present, the API will return a 403: Forbidden.

* email: user@eyenetra.com
* password: testPassword1

If the credentials are Visioneer credentials, the API will return a 200: Success.

* email: visioneer@eyenetra.com
* password: testPassword1

### Example Request

````
curl
-H "Content-Type: application/json"
-d '{"email":"visioneer@eyenetra.com","password":"testPassword1"}'
https://dev-portal-api.eyenetra.com:7443/api/v1/tablet_login
````

Parameters: you provide request parameters as JSON in your request's body

````
{
  "email":"me@mail.com",
  "password":"myPassword1"
}
````

### Example Response

````
{
  "info":"Success",
  "token":"123456......abcdef",
  "firstName":"Me"
}
````

-----

## Tablet Logout

````
DELETE /api/v1/tablet_logout
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
