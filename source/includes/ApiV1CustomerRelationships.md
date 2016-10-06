# Customer Relationships

**Customer Relationships** are created between ODs and customers. ODs can only see a customer personal information if they already have this relationship. Because of that, ODs can't see personal information of new/unassigned customers and/or customers assigned to another OD.

#### Structure

* id
* customer_id
* payment_id
* status
* decision
* created_at
* updated_at

<aside class="warn">
All requests require <a href="#basic-authentication">authentication</a>.
</aside>

## Select New Customer

### HTTP Request

`GET /api/v1/select_new_customer`

Note: user must be an OD, else the response will be 403 Forbidden

> https://dev-portal-api.eyenetra.com:7443/api/v1/select_new_customer

````
{
  "id":5,
  "customer_id":35,
  "payment_id":77,
  "status":"incomplete",
  "decision":"undecided",
  "created_at":"2014-12-23T19:23:56.824Z",
  "updated_at":"2014-12-23T19:23:56.824Z"
}
````

