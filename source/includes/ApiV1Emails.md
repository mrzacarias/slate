# Emails

> Email Structure Example

````
{ 
  "emails": {
    "id": 7, 
    "template_name": "blink-od-prescribed", 
    "template_content": {
      "email": "Leda.Stiedemann18@gmail.com", 
      "name": "Jerad", 
      "vars": {
        "first_name": "Jerad", 
        "link": "https://me.eyenetra.com/visits/402"
      }
    }, 
    "visit_id": 17,
    "status": "sent", 
    "created_at": "2015-02-03T22:16:02.302Z", 
    "updated_at": "2015-02-03T22:16:02.302Z"
  }
}
````

List of **Emails** sent to the customer of a specific visit.

<aside class="warn">
All requests require <a href="#basic-authentication">authentication</a>.
</aside>

## Filtered List

> Response Example 

````
{ 
  "emails": [ 
    {
      "id": 7, 
      "template_name": "blink-od-prescribed", 
      "template_content": {
        "email": "Leda.Stiedemann18@gmail.com", 
        "name": "Jerad", 
        "vars": {
          "first_name": "Jerad", 
          "link": "https://me.eyenetra.com/visits/402"
        }
      }, 
      "visit_id": 17,
      "status": "sent", 
      "created_at": "2015-02-03T22:16:02.302Z", 
      "updated_at": "2015-02-03T22:16:02.302Z"
    }
  ]
}
````

`GET https://insight-api.eyenetra.com/api/v1/emails?visit_id=[visit id]`
