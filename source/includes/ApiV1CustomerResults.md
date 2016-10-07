# Customer Results

> Customer Result Structure Example

````
{
  "customer_result": {
    "id": "00000000-0000-0000-0000-000000000000",
    "status": "completed",
    "decision": "prescribed",
    "decision_note": "This is the decision note of the Magic Prescribed Customer!",
    "internal_note": "FOR INTERNAL USE ONLY",
    "customer_id": 3,
    "test_confidence": null,
    "distance_preference": null,
    "near_preference": null,
    "predisposition": null,
    "uuid": "00000000-0000-0000-0000-000000000000",
    "prescription_id": 1,
    "intake_form_id": 2,
    "appointment_id": null,
    "contacts_id": null,
    "screening_id": null,
    "netra_id": null,
    "netrometer_id": null,
    "visit_note_ids": ["..."],
    "prescribing_od_id": 5,
    "customer_relationship_ids": [5],
    "test_result_ids": ["..."],
    "created_at": "2016-06-20T19:51:41.963Z",
    "updated_at": "2016-06-20T19:51:42.115Z",
    "organization_id": 1
  }
}
````

These are the **Customer Results** after his assigned OD had a decision based on the customer's test results. It's used to build the customer results page, where the customer can print his prescription and use it to order new glasses.

<aside class="warn">
All requests require <a href="#basic-authentication">authentication</a>.
</aside>

## Show

> Response Example 

````
{
  "customer_result": {
    "id": "00000000-0000-0000-0000-000000000000",
    "created_at": "2016-06-20T19:51:41.963Z",
    "updated_at": "2016-06-20T19:51:42.115Z",
    "status": "completed",
    "decision": "prescribed",
    "decision_note": "This is the decision note of the Magic Prescribed Customer!",
    "internal_note": "FOR INTERNAL USE ONLY",
    "customer_id": 3,
    "test_confidence": null,
    "distance_preference": null,
    "near_preference": null,
    "predisposition": null,
    "uuid": "00000000-0000-0000-0000-000000000000",
    "prescription_id": 1,
    "intake_form_id": 2,
    "appointment_id": null,
    "contacts_id": null,
    "screening_id": null,
    "netra_id": null,
    "netrometer_id": null,
    "visit_note_ids": ["..."],
    "prescribing_od_id": 5,
    "customer_relationship_ids": [5],
    "test_result_ids": ["..."],
    "organization_id": 1
  }
}
````

### HTTP Request

`GET https://insight-api.eyenetra.com/api/v1/customer_results/<uuid>`

Note: if the uuid is not valid (no customer with a prescription with this uuid is found), a 404 status is returned.
