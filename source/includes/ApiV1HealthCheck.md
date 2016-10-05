# Health Check

**Health check** verification without authorization requirement.

#### Authentication

Not required.

-----

## Index

````
GET /api/v1/health_check
````

* version: [semver](http://semver.org) formatted string

### Example Request

````
https://dev-portal-api.eyenetra.com:7443/api/v1/health_check
````

### Example Response

````
{
  "version":"0.3.0"
}
````
