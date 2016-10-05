# Visits

* [List](#list)
* [Show](#show)
* [Update](#update)

A _**Visit**_ represents a single interaction between a customer and us. Visits are the primary workflow element for ODs and CSRs in our model. With a visit, you can get to a customer, a prescription, and payments.

#### Structure

 * id
 * customer_id
 * created_at
 * updated_at
 * status
 * decision
 * decision_note
 * test_confidence
 * distance_preference
 * near_preference
 * screening_id
 * netra_id
 * predisposition
 * uuid
 * contacts_id
 * internal_note
 * organization_id
 * netrometer_id

#### Authentication

All requests require [authentication](ApiV1BasicAuthentication).

------

## List

````
GET /api/v1/visits
````

Get a list of visits. 

### Example Request

````
https://dev-portal-api.eyenetra.com:7443/api/v1/visits
````

Obs.: To CSV exported data, add .csv as the format.

### Example Response

````
{
  "visits": [
    {
      "id": 101,
      "customer_id": 101,
      "created_at": "2015-11-13T20:37:05.425Z",
      "updated_at": "2015-11-13T20:37:05.425Z",
      "status": "new",
      "decision": null,
      "decision_note": null,
      "test_confidence": "HIGH",
      "distance_preference": "NETRA",
      "near_preference": "SCREENING",
      "screening_id": 192,
      "netra_id": 193,
      "predisposition": null,
      "uuid": "a7916e20-79c2-460a-b4e7-d4926825dfe0",
      "contacts_id": null,
      "internal_note": null,
      "organization_id": 1,
      "netrometer_id": null
    },
    {...}
    {
      "id": 110,
      "customer_id": 110,
      "created_at": "2015-11-13T20:37:05.425Z",
      "updated_at": "2015-11-13T20:37:05.425Z",
      "status": "completed",
      "decision": "prescribed",
      "decision_note": "Congratulations, you have a new prescription!",
      "test_confidence": "HIGH",
      "distance_preference": "NETRA",
      "near_preference": "NETRA",
      "screening_id": 194,
      "netra_id": 195,
      "predisposition": null,
      "uuid": "a7916e20-79c2-460a-b4e7-d4926825dfe0",
      "contacts_id": null,
      "internal_note": null,
      "organization_id": 1,
      "netrometer_id": null
    }
  ],
  "meta": {
    "previous": null,
    "next": 2,
    "stats": {
      "oldestNewStatus": "critical",
      "oldestIncompleteStatus": "critical",
      "new": 47,
      "incomplete": 43,
      "completed": 61
    }
  }
}
````

### Filters

The following columns are available for filtering: 
* status
* decision
* decision_note
* test_confidence
* distance_preference
* near_preference
* predisposition
* uuid
* internal_note
* created_at
* updated_at

````
https://dev-portal-api.eyenetra.com:7443/api/v1/visits?test_confidence=HIGH
````

### Searching

You can use the param "q" (for query) to set a string that will be used to search alike entries (case insensitive, using SQL "LIKE" command) on the following columns:
* status
* decision
* decision_note
* test_confidence
* distance_preference
* near_preference
* uuid
* internal_note

````
https://dev-portal-api.eyenetra.com:7443/api/v1/visits?q=congratulations
````

### Sorting

The same columns used for filtering can be used for sorting. To sort your request, you pass the column name on the parameter "sort":

````
https://dev-portal-api.eyenetra.com:7443/api/v1/visits?sort=uuid
````

The default order when passing a parameter is ascending, you can change for descending passing a "-" before the column name:

````
https://dev-portal-api.eyenetra.com:7443/api/v1/visits?sort=-uuid
````

The default sort for requests is "-updated_at".

### "Since" parameters

You can also set "updated_since" or "created_since" parameters, specifying a bottom limit date or date/time to your requests

````
https://dev-portal-api.eyenetra.com:7443/api/v1/visits?test_confidence=LOW&sort=-uuid&updated_since="01-01-2016"
````
------

## Show

````
GET /api/v1/visits/:id
````

### Example Request

````
https://dev-portal-api.eyenetra.com:7443/api/v1/visits/1
````

Obs.: To CSV exported data, add .csv as the format.

### Example Response

Sideloads: 
  * prescriptions
  * intake forms

This call presumes you already know about customers, so it does not return a sideload of them.

````
{
  "visit": {
    "id": 1,
    "created_at": "2015-11-13T15:36:56.907Z",
    "updated_at": "2015-11-13T15:36:56.907Z",
    "status": "incomplete",
    "decision": null,
    "decision_note": null,
    "internal_note": null,
    "customer_id": 2,
    "test_confidence": null,
    "distance_preference": null,
    "near_preference": null,
    "predisposition": null,
    "uuid": "77bb7235-90e6-4c2a-bf30-fe5e27e60731",
    "prescription_id": null,
    "intake_form_id": 1,
    "contacts_id": null,
    "screening_id": null,
    "netra_id": null,
    "visit_note_ids": [],
    "prescribing_od_id": null,
    "customer_relationship_ids": [5]
  }
}
````

------

## Update

````
PATCH /api/v1/visits/:id
````

Update a visit, for example to mark a decision. 

### Example Request
````
https://dev-portal-api.eyenetra.com:7443/api/v1/visits/1
````

````
{
  visit: 
    {
      customer_id: 12, 
      status: "complete", 
      decision: "prescribed"
    }
}
````

### Example Response
```
{
  visit: 
    {
      id: 12, 
      customer_id: 12, 
      created_at: 'Fri, 27 Feb 2015 22:18:38 UTC +00:00', 
      updated_at: 'Fri, 27 Feb 2015 22:18:38 UTC +00:00', 
      status: "complete", 
      decision: "prescribed"
    }
}
```
