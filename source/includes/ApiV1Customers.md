# Customers

These endpoints returns Eyenetra's **Customers** personal information as list or specific instance. The **"Select New Customer"** endpoint, though, is responsible to create an [customer relationship](ApiV1CustomerRelationships) between the current OD and the next new customer in line.

### Structure

Field           | Description
--------------- | -------------------------------------------------------------------------------
id              | The Appointment object ID
first_name      | TODO
last_name       | TODO
email           | TODO
phone           | TODO
address         | TODO
city            | TODO
state           | TODO
zip_code        | TODO
created_at      | TODO
updated_at      | TODO

<aside class="warn">
All requests require <a href="#basic-authentication">authentication</a>.
</aside>

## List

### HTTP Request

`GET /api/v1/customers`

> https://dev-portal-api.eyenetra.com:7443/api/v1/customers?decision=prescribed

Obs.: To CSV exported data, add .csv as the format.

````
{
  "customers": [
    {
      "id":1,
      "first_name":"Pixel",
      "last_name":"Purrfect",
      "email":"pixel@yahoo.com",
      "phone":"6171111223",
      "address":"35 Medford St",
      "city":"Boston",
      "state":"MA",
      "zip_code":"02143",
      "created_at":"2014-12-23T19:23:56.824Z",
      "updated_at":"2014-12-23T19:23:56.824Z"
    },{
      "id":2,
      "first_name":"Milk",
      "last_name":"Cookie",
      "email":"milk@hotmail.com",
      "phone":"6171122334",
      "address":"111 State St",
      "city":"Boston",
      "state":"MA",
      "zip_code":"02109",
      "created_at":"2014-12-23T19:23:56.830Z",
      "updated_at":"2014-12-23T19:23:56.830Z"
    }
  ]
}
````

## Filtering, Searching and Sorting

### Filters

> https://dev-portal-api.eyenetra.com:7443/api/v1/customers?email=johndoe@email.com

The following columns are available for filtering: 
* decision - Only for customers with visits, valid decisions: none, passed, prescribed, referred
* first_name
* last_name
* email
* phone
* address
* city
* state
* zip_code
* created_at
* updated_at

### Searching

> https://dev-portal-api.eyenetra.com:7443/api/v1/customers?q=John

You can use the param "q" (for query) to set a string that will be used to search alike entries (case insensitive, using SQL "LIKE" command) on the following columns:
* first_name
* last_name
* email
* phone
* address
* city
* state
* zip_code

### Sorting

> https://dev-portal-api.eyenetra.com:7443/api/v1/customers?sort=first_name

The same columns used for filtering can be used for sorting. To sort your request, you pass the column name on the parameter "sort":

> https://dev-portal-api.eyenetra.com:7443/api/v1/customers?sort=-first_name

The default order when passing a parameter is ascending, you can change for descending passing a "-" before the column name:

The default sort for requests is "-updated_at".

### "Since" parameters

> https://dev-portal-api.eyenetra.com:7443/api/v1/customers?q=john&sort=-email&updated_since="01-01-2016"

You can also set "updated_since" or "created_since" parameters, specifying a bottom limit date or date/time to your requests

## Show

### HTTP Request

`GET /api/v1/customers/<id>`

Note: user must be at least a CSR or in the case of an OD, have a relationship with the customer, else the response will be 403 Forbidden

* id
* first_name
* last_name
* created_at
* updated_at

The following fields are included only if CSR or Admin level access:
* email
* phone
* address
* city
* state
* zip_code

> https://dev-portal-api.eyenetra.com:7443/api/v1/customers/5

Obs.: To CSV exported data, add .csv as the format.

````
{
  "customer": [
    {
      "id":5,
      "first_name":"Pixel",
      "last_name":"Purrfect",
      "email":"pixel@yahoo.com",
      "phone":"6171111223",
      "address":"35 Medford St",
      "city":"Boston",
      "state":"MA",
      "zip_code":"02143",
      "created_at":"2014-12-23T19:23:56.824Z",
      "updated_at":"2014-12-23T19:23:56.824Z"
    }
  ]
}
````

## Select New Customer

`GET /api/v1/select_new_customer`

Note: user must be an OD, else the response will be 403 Forbidden

* id
* customer_id
* payment_id
* status
* decision
* created_at
* updated_at

> https://dev-portal-api.eyenetra.com:7443/api/v1/select_new_customer

````
{
  "id":5,
  "customer_id":35,
  "payment_id":77,
  "status":"incomplete",
  "decision":"undecided",
  "created_at":"2014-12-23T19:23:56.824Z",
  "updated_at":"2014-12-23T19:23:56.824Z"
}
````
