# SignUp

After a customer bought a Netra product, he needs  to **SignUp** to start using his new device. This sign up are responsible to create a organization which encapsulates all the data of this new user, as the user instance itself.

#### Authentication

For now, not required.

## Create

### HTTP Request

`POST /api/v1/sign_up/`

> https://dev-portal-api.eyenetra.com:7443/api/v1/sign_up/

````
{
  "sign_up": {
    "organization": {
      "name": "Test Organization" },
    "user": {
      "first_name": "First",
      "last_name": "Last",
      "email": "test@createorg.com",
      "password": "createorgPassword1",
      "role": "admin"
    }
  }
}
````

````
{
  "organization": {
    "id": 1055,
    "name": "Test Organization",
    "kind": "single_OD",
    "logo": null,
    "template": null,
    "created_at": "2016-09-30T19:50:47.626Z",
    "updated_at": "2016-09-30T19:50:47.626Z",
    "status": "ok",
    "plan": null,
    "description": null,
    "address1": null,
    "address2": null,
    "zip_code": null,
    "city": null,
    "state": null,
    "country": null,
    "prescribed_message": null,
    "passed_message": null,
    "referred_message": null,
    "subscription_id": null,
    "reminder_message": null,
    "thanks_message": null
  },
  "user": {
    "id": 2115,
    "first_name": "First",
    "last_name": "Last",
    "email": "test@createorg.com",
    "password_digest": "$2a$10$aWQRb7VpV8K5ENEJ1N/tke3l9ICf2Nn3ExQkOuTJI.RTXQgnwughu",
    "created_at": "2016-09-30T19:50:47.700Z",
    "updated_at": "2016-09-30T19:50:47.735Z",
    "api_key_id": null,
    "signature": null,
    "title": null,
    "npi": null,
    "license_number": null,
    "license_state": null,
    "organization_id": 1055,
    "longitude": null,
    "latitude": null,
    "photo_url": null,
    "description": null,
    "group_id": null,
    "deleted": false,
    "locale": "en-US"
  },
  "token": "d75f861ed4401338b736ac4849d80862"
}
````
