# TeleRx Flow

* [Create](#create)

The **TeleRx Flow** endpoint is responsible to save all the data acquired during a complete visit (readings, customer information, etc.) on the insight database.

#### Authentication

All requests require [tablet authentication](ApiV1TabletAuthentication).

-----

## Create
  
````
POST /api/v1/telerx_flow
````

### Data structure

* data
    * customer
        * email (required)
        * firstName (required)
        * lastName
        * phone
        * address
        * city
        * state
        * zipCode

### Example Request

````
https://dev-portal-api.eyenetra.com:7443/api/v1/telerx_flow
````

Body

````
{
  "data": { 
    "customer": {
      "email":"me@myemail.com",
      "firstName":"Megan",
      "lastName":"Smith",
      "phone":"6173334444",
      "address":"123 Main St.",
      "city":"Waltham",
      "state":"MA",
      "zipCode":"02451"
    }
  }
}
````

#### Original TeleRx Flow Data will be accepted

````
{
  "Customer": {
    "sync_id": "980de666-8abf-42be-aad7-2662656d202e",
    "phone": "121-378-7964",
    "zip_code": "",
    "prescription_selected": true,
    "departure_reason": "",
    "state": "",
    "prescription_price": 0,
    "city": "",
    "version": 1,
    "first_name": "New",
    "address": "",
    "email": "customeremail@hotmail.com",
    "screening_price": 0,
    "last_name": "Customer"
  }
}
````

Header:

````
Content-Type: application/json
Authorization: Token token="123456......abcdef"

````

### Example Response
````
{
  "info":"Success"
}
````
