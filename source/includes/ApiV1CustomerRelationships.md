# Customer Relationships

**Customer Relationships** are created between ODs and customers. ODs can only see a customer personal information if they already have this relationship. Because of that, ODs can't see personal information of new/unassigned customers and/or customers assigned to another OD.

<aside class="warn">
All requests require <a href="#basic-authentication">authentication</a>.
</aside>

## Select New Customer

> Response Example 

````
{
  "id":5,
  "customer_id":35,
  "status":"incomplete",
  "decision":"undecided",
  "created_at":"2014-12-23T19:23:56.824Z",
  "updated_at":"2014-12-23T19:23:56.824Z"
}
````

### HTTP Request

`GET https://insight-api.eyenetra.com/api/v1/select_new_customer`

Note: user must be an OD, else the response will be 403 Forbidden
