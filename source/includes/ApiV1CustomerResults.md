# Customer Results

These are the **Customer Results** after his assigned OD had a decision based on the customer's test results. It's used to build the customer results page, where the customer can print his prescription and use it to order new glasses.

#### Structure

 * id
 * left_cyl
 * left_add
 * left_prism
 * left_sph
 * right_cyl
 * right_add
 * right_prism
 * right_sph
 * pd
 * near_pd
 * note
 * uuid
 * recommended_use

<aside class="warn">
All requests require <a href="#basic-authentication">authentication</a>.
</aside>

## Show

### HTTP Request

`GET /api/v1/customer_results/<uuid>`

Note: if the uuid is not valid (no customer with a prescription with this uuid is found), a 404 status is returned.

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
    "visit_note_ids": [],
    "prescribing_od_id": 5,
    "customer_relationship_ids": [5],
    "test_result_ids": [],
    "organization_id": 1
  },
  "roles": [...],
  "appointments": [...],
  "prescribing_ods": [...],
  "prescriptions": [
    {
      "id": 1,
      "left_sph": -1.25,
      "left_cyl": 0.4,
      "left_axis": 180,
      "left_add": -2,
      "right_sph": 1.25,
      "right_cyl": -0.5,
      "right_axis": 90,
      "right_add": 2.5,
      "pd": 65,
      "near_pd": 62,
      "recommended_use": "Near",
      "prescribing_od_id": 5
    }
  ],
  "intake_forms": [...],
  "test_results": [...],
  "visit_note": [...],
  "customer_relationship": [...],
  "visits": [
    {
      "id": 2,
      "created_at": "2016-06-20T19:51:41.963Z",
      "updated_at": "2016-06-20T19:51:42.115Z",
      "status": "completed",
      "decision": "prescribed",
      "decision_note": "This is the decision note of the Magic Prescribed Customer!",
      "internal_note": null,
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
      "visit_note_ids": [],
      "prescribing_od_id": 5,
      "customer_relationship_ids": [
        5
      ],
      "test_result_ids": []
    }
  ],
  "customers": [
    {
      "id": 3,
      "first_name": "Ammo",
      "last_name": "Bigglesworth",
      "email": "ammo@example.com",
      "phone": "2121122344",
      "address": "45 Rockefeller Plaza",
      "city": "New York",
      "state": "NY",
      "zip_code": "10111",
      "created_at": "2016-06-20T19:51:40.105Z",
      "updated_at": "2016-06-20T19:51:42.118Z",
      "birthdate": "1950-01-01",
      "visit_ids": [
        2
      ]
    }
  ],
  "users": [...],
  "organizations": [...],
}
````
