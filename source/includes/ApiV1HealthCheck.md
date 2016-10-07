# Health Check

**Health check** verification without authorization requirement.

<aside class="warn">
Do not require <a href="#basic-authentication">authentication</a>.
</aside>

## Index

### HTTP Request

> Response Example 

````
{
  "version":"0.3.0"
}
````

`GET https://insight-api.eyenetra.com/api/v1/health_check`

* version: [semver](http://semver.org) formatted string
