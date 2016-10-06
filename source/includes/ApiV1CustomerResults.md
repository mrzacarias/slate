# Customer Results

> Customer Result Structure Example

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

These are the **Customer Results** after his assigned OD had a decision based on the customer's test results. It's used to build the customer results page, where the customer can print his prescription and use it to order new glasses.

### Structure

Field               | Description
------------------- | -----------------------------------------------------------------------------
id                  | The Visit UUID
status              | TODO
decision            | TODO
decision_note       | TODO
internal_note       | TODO
customer_id         | TODO
test_confidence     | TODO
distance_preference | TODO
near_preference     | TODO
predisposition      | TODO
uuid                | TODO
prescription_id     | TODO
intake_form_id      | TODO
appointment_id      | TODO
contacts_id         | TODO
screening_id        | TODO
netra_id            | TODO
netrometer_id       | TODO
visit_note_ids      | TODO
prescribing_od_id   | TODO
customer_relationship_ids         | TODO
test_result_ids     | TODO
organization_id     | TODO
created_at          | TODO
updated_at          | TODO

<aside class="warn">
All requests require <a href="#basic-authentication">authentication</a>.
</aside>

## Show

> https://dev-portal-api.eyenetra.com:7443/api/v1/customer_results/00000000-0000-0000-0000-000000000000

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

`GET /api/v1/customer_results/<uuid>`

Note: if the uuid is not valid (no customer with a prescription with this uuid is found), a 404 status is returned.
