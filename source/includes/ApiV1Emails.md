# Emails

List of **Emails** sent to the customer of a specific visit.

#### Structure

 * id
 * template_name
 * template_content
   * email
   * name
   * vars
     * first_name
     * link
 * visit_id
 * status
 * created_at
 * updated_at


#### Authentication

All requests require [authentication](ApiV1BasicAuthentication).

-----

## Filtered List

````
GET /api/v1/emails?visit_id=[visit id]
````

### Example Request

````
https://dev-portal-api.eyenetra.com:7443/api/v1/emails?visit_id=123
````

### Example Response

````
{ 
  "emails"=>
    [ {
        "id"=>7, 
        "template_name"=>"blink-od-prescribed", 
        "template_content"=>"{
          :email=>"Leda.Stiedemann18@gmail.com", 
          :name=>"Jerad", 
          :vars=>{
            :first_name=>"Jerad", 
            :link=>"https://me.eyenetra.com/visits/402"
          }
        }", 
        "visit_id"=>17
        "status"=>"sent", 
        "created_at"=>"2015-02-03T22:16:02.302Z", 
        "updated_at"=>"2015-02-03T22:16:02.302Z", 
    } ]
}
````
