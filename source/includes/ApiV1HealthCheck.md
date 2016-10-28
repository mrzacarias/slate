# Health Check

**Health check** verification without authorization requirement.

<aside class="warn">
Do not require <a href="#basic-authentication">authentication</a>.
</aside>

## Index

> Response Example 

````
{
  "version":"0.3.0"
}
````

This endpoint is just a very basic API health check, used normally on tests to verify the API current version.

### HTTP Request

`GET https://insight-api.eyenetra.com/api/v1/health_check`

* version: [semver](http://semver.org) formatted string
