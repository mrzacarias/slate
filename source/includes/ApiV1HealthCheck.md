# Health Check

**Health check** verification without authorization requirement.

<aside class="warn">
Do not require <a href="#basic-authentication">authentication</a>.
</aside>

## Index

### HTTP Request

> https://dev-portal-api.eyenetra.com:7443/api/v1/health_check

````
{
  "version":"0.3.0"
}
````

`GET /api/v1/health_check`

* version: [semver](http://semver.org) formatted string
