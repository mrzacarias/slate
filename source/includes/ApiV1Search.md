# Search

> Search result Structure Example

````
{
  "customers": ["..."],
  "readings": ["..."],
  "visits": ["..."]
}
````

**Search** is the endpoint to make general queries that will return customers, readings and visits related to the term passed as argument.

<aside class="warn">
All requests require <a href="#basic-authentication">authentication</a>.
</aside>

## Query

> Response Example 

````
{
  "customers": [
    {
      "id": 80,
      "first_name": "Wilmer",
      "last_name": "Testing",
      "email": "ruby-devs-f1a01239-e0da-4859-8a5e-14499cb180f1@goblink.co",
      "phone": "1234567890",
      "address": "",
      "city": "",
      "state": "",
      "zip_code": "",
      "created_at": "2016-06-20T22:11:07.811Z",
      "updated_at": "2016-06-20T22:11:07.811Z",
      "birthdate": "1950-01-01",
      "organization_id": 1
    }
  ],
  "readings": [],
  "visits": [
    {
      "id": 37,
      "customer_id": 19,
      "created_at": "2016-06-20T19:56:31.620Z",
      "updated_at": "2016-06-20T22:07:14.255Z",
      "status": "completed",
      "decision": "passed",
      "decision_note": "Test pass note",
      "test_confidence": null,
      "distance_preference": null,
      "near_preference": null,
      "screening_id": null,
      "netra_id": null,
      "predisposition": null,
      "uuid": "8f4af320-558b-47e4-aac9-fbeb1a08568a",
      "contacts_id": null,
      "internal_note": "Test internal pass note",
      "organization_id": 1,
      "netrometer_id": null,
      "prescribing_od_id": 5
    }
  ]
}
````

The API will search the query term on customers, readings and visits entries.

Note: There's no fuzzy logic (yet).

### HTTP Request

`GET https://insight-api.eyenetra.com/api/v1/search?q={query}`
