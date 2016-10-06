# Emails

List of **Emails** sent to the customer of a specific visit.

### Structure

Field            | Description
---------------- | -------------------------------------------------------------------------------
id               | The Appointment object ID
template_name    | TODO
template_content | TODO
visit_id         | TODO
status           | TODO
created_at       | TODO
updated_at       | TODO

<aside class="warn">
All requests require <a href="#basic-authentication">authentication</a>.
</aside>

## Filtered List

`GET /api/v1/emails?visit_id=[visit id]`

> https://dev-portal-api.eyenetra.com:7443/api/v1/emails?visit_id=123

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
