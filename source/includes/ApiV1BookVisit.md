# Book Visit

The **Book Visit** endpoint is the most importante input entry on our API, responsible to save all 
the data acquired during a complete visit (readings, customer information, appointment, etc.)
on the insight database.

<aside class="warn">
Do not require <a href="#basic-authentication">authentication</a>.
</aside>

## Create

> Request Body

````
{
  "book_visit": {
    "user": { "id": "5" },
    "customer": {
      "first_name": "test",
      "last_name": "test",
      "email": "test@test.com",
      "birthdate": "January 1, 1950"
    },
    "intake": {
      "occupation": "test",
      "is_driver": false,
      "eye_brain_surgery": false,
      "additional_info": "test",
      "prescriptions": "test",
      "vision_insurance": "No",
      "hear_about_us": "Word of mouth",
      "last_eye_exam": "Less than 6 months",
      "how_wear_glasses": "No Glasses",
      "age_glasses": "Prescribed at last eye exam",
      "current_eyewear": ["Nothing", "Constant Wear Glasses", "Distance Only Glasses", "Readers", "Bifocals", "Progressives", "Contacts", "Unknown"],
      "reasons_for_visit_eyewear": {
        "Near vision trouble": "Any eyewear",
        "Distance vision trouble": "Any eyewear",
        "Computer eye fatigue": "Any eyewear",
        "Reading eye fatigue": "Any eyewear",
        "Checkup": "Any eyewear",
        "Prescription renewal": "Any eyewear"
      },
      "eye_symptoms": ["Amblyopia", "Blurred Vision", "Distorted Vision Halos", "Double Vision", "Dryness In Eyes", "Eye Pain", "Eyelid Infection", "Eye Burn", "Eye Injury", "Eye Itch", "Eyes Light Sensitives", "Eyes Water Tear", "Fluctuating Vision", "Foreign Body Feeling", "Lazy Eye", "Loss Of Vision", "Mucuos In Eyes", "Redness In Eyes", "Sandy Feeling", "Stye", "Tired Eyes"],
      "health_conditions": ["HIV", "Arthritis", "Blindness", "Cancer", "Cataracts", "Corneal Disease", "Diabetes", "Glaucoma", "Heart Disease", "High Blood Pressure", "High Cholesterol", "Kidney Disorder", "Lupus", "Macular Degeneration", "Retinal Disorder", "Sjogrens Syndrome", "Stroke", "Thyroid Disease", "Turned Eye Strabismus"]
    },
    "appointment": {
      "title": "test test",
      "start": "2016-10-06T11:00:00",
      "end": "2016-10-06T12:00:00"
    }
  }
}
````

> Response Example 

````
{
  "visit": {
    "id": 17314,
    "customer_id": 12172,
    "created_at": "2016-09-30T20:09:47.383Z",
    "updated_at": "2016-09-30T20:09:47.401Z",
    "status": "incomplete",
    "decision": null,
    "decision_note": null,
    "test_confidence": null,
    "distance_preference": null,
    "near_preference": null,
    "screening_id": null,
    "netra_id": null,
    "predisposition": null,
    "uuid": "e877eb12-188e-4fec-9edc-b64888a6eca4",
    "contacts_id": null,
    "internal_note": null,
    "organization_id": 1,
    "netrometer_id": null,
    "prescribing_od_id": 5
  },
  "customer": {
    "id": 12172,
    "first_name": "test",
    "last_name": "test",
    "email": "test@test.com",
    "phone": null,
    "address": null,
    "city": null,
    "state": null,
    "zip_code": null,
    "created_at": "2016-09-07T21:10:38.964Z",
    "updated_at": "2016-09-07T21:10:38.964Z",
    "birthdate": "1950-01-01",
    "organization_id": 1
  },
  "intake_form": {
    "id": 17311,
    "is_driver": false,
    "eye_brain_surgery": false,
    "terms_accepted_on": null,
    "occupation": "test",
    "prescriptions": "test",
    "inches_from_screen": null,
    "last_eye_exam": "Less than 6 months",
    "visit_id": 17314,
    "created_at": "2016-09-30T20:09:47.375Z",
    "updated_at": "2016-09-30T20:09:47.386Z",
    "eye_symptoms": ["Amblyopia", "Blurred Vision", "Distorted Vision Halos", "Double Vision", "Dryness In Eyes", "Tired Eyes", "Stye", "Sandy Feeling", "Redness In Eyes", "Mucuos In Eyes"],
    "requested_eyewear": [],
    "health_conditions": ["HIV", "Arthritis", "Blindness", "Cancer", "Cataracts", "Turned Eye Strabismus", "Thyroid Disease", "Stroke", "Sjogrens Syndrome", "Retinal Disorder"],
    "current_eyewear": ["Readers", "Distance Only Glasses", "Contacts", "Bifocals", "Progressives", "Constant Wear Glasses"],
    "reasons_for_visit_eyewear": {
      "Near vision trouble": "Any eyewear",
      "Computer eye fatigue": "Any eyewear",
      "Distance vision trouble": "Any eyewear",
      "Checkup": "Any eyewear",
      "Reading eye fatigue": "Any eyewear",
      "Prescription renewal": "Any eyewear"
    },
    "has_driving_vision_trouble": null,
    "vision_insurance": "No",
    "hear_about_us": "Word of mouth",
    "how_wear_glasses": "No Glasses",
    "age_glasses": "Prescribed at last eye exam",
    "additional_info": "test"
  },
  "appointment": {
    "id": 46,
    "title": "test test",
    "start": "2016-10-05T14:00:00.000Z",
    "end": "2016-10-05T15:00:00.000Z",
    "user_id": 5,
    "visit_id": 17314,
    "created_at": "2016-09-30T20:09:47.430Z",
    "updated_at": "2016-09-30T20:09:47.430Z",
    "organization_id": 1
  }
}
````

Using the book_visit create endpoint with the correct request body will save a visit on your organization database.
This visit will be already associated with the user passed on the parameters.
The apointment information will be loaded on the Visit request (List or Show) and on it's own endpoint.
If the customer email is already on Insight Database, his information will be updated. If not, a new patient/customer entry will be created.

### HTTP Request

`POST https://insight-api.eyenetra.com/api/v1/book_visit`

### Body Parameters

Parameter       | Description
--------------- | -------------------------------------------------------------------------------
user            | OD user ID to whom this visit will be related
customer        | Customer personal information
intake          | Customer intake information information
appointment     | Appointment information
