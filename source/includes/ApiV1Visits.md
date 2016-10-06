# Visits

A _**Visit**_ represents a single interaction between a customer and us. Visits are the primary workflow element for ODs and CSRs in our model. With a visit, you can get to a customer, a prescription, and payments.

### Structure

Field               | Description
------------------- | -----------------------------------------------------------------------------
id                  | The Appointment object ID
customer_id         | TODO
created_at          | TODO
updated_at          | TODO
status              | TODO
decision            | TODO
decision_note       | TODO
test_confidence     | TODO
distance_preference | TODO
near_preference     | TODO
screening_id        | TODO
netra_id            | TODO
predisposition      | TODO
uuid                | TODO
contacts_id         | TODO
internal_note       | TODO
organization_id     | TODO
netrometer_id       | TODO

<aside class="warn">
All requests require <a href="#basic-authentication">authentication</a>.
</aside>

## List

### HTTP Request

`GET /api/v1/visits`

Get a list of visits. 

> https://dev-portal-api.eyenetra.com:7443/api/v1/visits

Obs.: To CSV exported data, add .csv as the format.

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
    }
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

## Filtering, Searching and Sorting

### Filters

> https://dev-portal-api.eyenetra.com:7443/api/v1/visits?test_confidence=HIGH

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

### Searching

> https://dev-portal-api.eyenetra.com:7443/api/v1/visits?q=congratulations

You can use the param "q" (for query) to set a string that will be used to search alike entries (case insensitive, using SQL "LIKE" command) on the following columns:
* status
* decision
* decision_note
* test_confidence
* distance_preference
* near_preference
* uuid
* internal_note

### Sorting

> https://dev-portal-api.eyenetra.com:7443/api/v1/visits?sort=uuid

The same columns used for filtering can be used for sorting. To sort your request, you pass the column name on the parameter "sort":

> https://dev-portal-api.eyenetra.com:7443/api/v1/visits?sort=-uuid

The default order when passing a parameter is ascending, you can change for descending passing a "-" before the column name:

The default sort for requests is "-updated_at".

### "Since" parameters

> https://dev-portal-api.eyenetra.com:7443/api/v1/visits?test_confidence=LOW&sort=-uuid&updated_since="01-01-2016"

You can also set "updated_since" or "created_since" parameters, specifying a bottom limit date or date/time to your requests

## Show

### HTTP Request

`GET /api/v1/visits/:id`

> https://dev-portal-api.eyenetra.com:7443/api/v1/visits/1

Obs.: To CSV exported data, add .csv as the format.

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

## Update

### HTTP Request

`PUT /api/v1/visits/:id`

Update a visit, for example to mark a decision. 

> https://dev-portal-api.eyenetra.com:7443/api/v1/visits/1

````
{
  "visit": 
    {
      "customer_id": 12, 
      "status": "complete", 
      "decision": "prescribed"
    }
}
````

````
{
  "visit": 
    {
      "id": 12, 
      "customer_id": 12, 
      "created_at": "Fri, 27 Feb 2015 22:18:38 UTC +00:00", 
      "updated_at": "Fri, 27 Feb 2015 22:18:38 UTC +00:00", 
      "status": "complete", 
      "decision": "prescribed"
    }
}
````
