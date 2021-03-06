# Intake Forms

> Intake Form Structure Example

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

**Intake Forms** contains the customer's professional and medical information that created a visit on Insight.
This visit can be created using the book visit request, with or without appointment information.

<aside class="warn">
All requests require <a href="#basic-authentication">authentication</a>.
</aside>

## Filtered List

> Response Example 

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
    }
  ]
}
````

The filtered request will return the list of intake forms that matches the customer information passed as parameter.

### HTTP Request

`GET https://insight-api.eyenetra.com/api/v1/intake_forms?filter[customers][email]=customer@mail.com`


## Show

> Response Example 

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

This show endpoint will return the intake form information correspondent to the intake form id passed as parameter.

### HTTP Request

`GET https://insight-api.eyenetra.com/api/v1/intake_forms/{id}`

