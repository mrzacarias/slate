# Intake Forms

**Intake Forms** information of visits uploaded via TeleRx flow.

#### Authentication

All requests require [authentication](ApiV1BasicAuthentication).

#### Structure

* id
* is_driver
* eye_brain_surgery
* terms_accepted_on
* occupation
* prescriptions
* inches_from_screen
* last_eye_exam
* visit_id
* eye_symptoms
* requested_eyewear
* health_conditions
* current_eyewear
* reasons_for_visit_eyewear
* has_driving_vision_trouble
* vision_insurance
* hear_about_us

-----

## Filtered List

````
GET /api/v1/intake_forms?filter[customers][email]=customer@mail.com
````

### Example Request

````
https://dev-portal-api.eyenetra.com:7443/api/v1/intake_forms?filter[customers][email]=milk@example.com
````

### Example Response

````
{
  "intake_forms": [
    {
      "id": 1,
      "is_driver": true,
      "eye_brain_surgery": false,
      "terms_accepted_on": "2016-06-18",
      "occupation": "CandlestickMaker",
      "prescriptions": "Zylitol",
      "inches_from_screen": 9,
      "last_eye_exam": "6 months ago",
      "visit_id": 1,
      "eye_symptoms": [],
      "age_glasses": null,
      "requested_eyewear": [
        "Bifocals",
        "Progressives"
      ],
      "health_conditions": [],
      "current_eyewear": [],
      "reasons_for_visit_eyewear": {},
      "has_driving_vision_trouble": null,
      "vision_insurance": null,
      "hear_about_us": null,
      "how_wear_glasses": null,
      "additional_info": null
    },
    {
      "id": 33,
      "is_driver": true,
      "eye_brain_surgery": true,
      "terms_accepted_on": "2016-06-12",
      "occupation": "CandlestickMaker",
      "prescriptions": "Sucralose",
      "inches_from_screen": 22,
      "last_eye_exam": "6 months ago",
      "visit_id": 33,
      "eye_symptoms": [],
      "age_glasses": null,
      "requested_eyewear": [
        "Bifocals",
        "Progressives"
      ],
      "health_conditions": [],
      "current_eyewear": [],
      "reasons_for_visit_eyewear": {},
      "has_driving_vision_trouble": null,
      "vision_insurance": null,
      "hear_about_us": null,
      "how_wear_glasses": null,
      "additional_info": null
    },
    ...
  ]
}
````
-----

## Show

````
GET /api/v1/intake_forms/{:intake_form_id}
````

### Example Request

````
https://dev-portal-api.eyenetra.com:7443/api/v1/intake_forms/58
````

### Example Response

````
{
  "intake_form": {
    "id": 1,
    "is_driver": true,
    "eye_brain_surgery": false,
    "terms_accepted_on": "2016-06-18",
    "occupation": "CandlestickMaker",
    "prescriptions": "Zylitol",
    "inches_from_screen": 9,
    "last_eye_exam": "6 months ago",
    "visit_id": 1,
    "eye_symptoms": [],
    "age_glasses": null,
    "requested_eyewear": ["Bifocals","Progressives"],
    "health_conditions": [],
    "current_eyewear": [],
    "reasons_for_visit_eyewear": {},
    "has_driving_vision_trouble": null,
    "vision_insurance": null,
    "hear_about_us": null,
    "how_wear_glasses": null,
    "additional_info": null
  }
}
````
