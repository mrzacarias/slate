# Customers

> Customer Structure Example

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

These endpoints returns Eyenetra's **Customers** personal information as list or specific instance.
The **"Select New Customer"** endpoint, though, is responsible to create an [customer relationship](ApiV1CustomerRelationships)
between the current OD and the next new customer in line.

### Structure

Field           | Description
--------------- | -------------------------------------------------------------------------------
id              | The object ID
first_name      | The Customer first name
last_name       | The Customer last name 
email           | The Customer email, used to send the e-prescription
phone           | The Customer phone
address         | The Customer address
city            | The Customer city
state           | The Customer state
zip_code        | The Customer zip_code
created_at      | When this object was created
updated_at      | Last time this objected was updated

<aside class="warn">
All requests require <a href="#basic-authentication">authentication</a>.
</aside>

## List

> Response Example 

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

### HTTP Request

`GET https://insight-api.eyenetra.com/api/v1/customers`

Obs.: To CSV exported data, add .csv as the format.


### Filters

`GET  https://insight-api.eyenetra.com/api/v1/customers?email=johndoe@email.com`

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

`GET  https://insight-api.eyenetra.com/api/v1/customers?q=John`

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

`GET  https://insight-api.eyenetra.com/api/v1/customers?sort=first_name`

The same columns used for filtering can be used for sorting. To sort your request, you pass the column name on the parameter "sort":

`GET  https://insight-api.eyenetra.com/api/v1/customers?sort=-first_name`

The default order when passing a parameter is ascending, you can change for descending passing a "-" before the column name:

The default sort for requests is "-updated_at".

### "Since" parameters

`GET  https://insight-api.eyenetra.com/api/v1/customers?q=john&sort=-email&updated_since="01-01-2016"`

You can also set "updated_since" or "created_since" parameters, specifying a bottom limit date or date/time to your requests

## Show

> Response Example 

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

This show endpoint will return the Customer information correspondent to the id passed as parameter.

### HTTP Request

`GET https://insight-api.eyenetra.com/api/v1/customers/<id>`

Obs.: To CSV exported data, add .csv as the format.

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
