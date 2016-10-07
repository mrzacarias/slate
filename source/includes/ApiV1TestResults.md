# Test Results

> Test Result Structure Example

````
{
  "test_result": {
    "id": 1,
    "longitude": null,
    "latitude": null,
    "uuid": null,
    "exam_date": null,
    "created_at": "2015-11-13T16:27:21.466Z",
    "updated_at": "2015-11-13T16:27:21.466Z",
    "distance_eyewear": "Constant wear glasses",
    "near_eyewear": "Constant wear glasses",
    "test_method": "Screening",
    "device_id": null,
    "app_version": null,
    "distance_binocular_id": 1,
    "near_binocular_id": 2,
    "notes": "This is the tag"
  }
}
````

The **Test Results** are the logic structure used to save the readings from Netra and Netrometer devices and, also, the customer's screening and contacts information.

### Structure

Field             | Description
----------------- | -------------------------------------------------------------------------------
id                | Id of this object
longitude         | Longitude coordinate where this reading was taken
latitude          | Latitude coordinate where this reading was taken
uuid              | UUID, used for sync
exam_date         | Date where this reading was taken
test_method       | Method or Device used to create this reading (Screening, contacts, Netra, Netrometer, etc.)
device_id         | ID of the device used
app_version       | Version of the APP (Netra or Netrometer)
distance_binocular_id | Distance binocular ID
near_binocular_id | Near binocular ID
notes             | Notes (Tags) added during the reading
created_at        | When this object was created
updated_at        | Last time this objected was updated

<aside class="warn">
All requests require <a href="#basic-authentication">authentication</a>.
</aside>

## List

> Response Example 

````
{
  "test_results": [
    {
      "id": 313,
      "test_method": "Netrometer",
      "distance_eyewear": null,
      "near_eyewear": null,
      "distance_binocular_id": 625,
      "near_binocular_id": null,
      "visit_id": null,
      "created_at": "2015-11-16T21:53:25.314Z",
      "updated_at": "2015-11-16T21:53:25.314Z",
      "retinal_sync_id": null,
      "retinal_protocol_version": null,
      "organization_id": 1,
      "longitude": "-71.08785",
      "latitude": "42.374336",
      "uuid": "23aaf627-076c-459d-a563-0581bf382e90",
      "exam_date": "2015-10-30T18:11:49.000Z",
      "device_id": "-1.0",
      "app_version": "0.5.1",
      "notes": "This is the tag"
    }
  ]
}
````

### HTTP Request

`GET https://insight-api.eyenetra.com/api/v1/test_results/`

Obs.: To CSV exported data, add .csv as the format.


### Filters

`GET  https://insight-api.eyenetra.com/api/v1/test_results?test_method=Netrometer`

The following columns are available for filtering: 

* test_method
* distance_eyewear
* near_eyewear
* longitude
* latitude
* uuid
* exam_date
* device_id
* app_version
* notes (TAG)
* created_at
* updated_at

### Searching

`GET  https://insight-api.eyenetra.com/api/v1/test_results?q=netra`

You can use the param "q" (for query) to set a string that will be used to search alike entries (case insensitive, using SQL "LIKE" command) on the following columns:

* test_method
* distance_eyewear
* near_eyewear
* uuid
* exam_date
* device_id
* app_version
* notes (TAG)

### Sorting

`GET  https://insight-api.eyenetra.com/api/v1/test_results?sort=app_version`

The same columns used for filtering can be used for sorting. To sort your request, you pass the column name on the parameter "sort":

`GET  https://insight-api.eyenetra.com/api/v1/test_results?sort=-app_version`

The default order when passing a parameter is ascending, you can change for descending passing a "-" before the column name:

The default sort for requests is "-updated_at".

### "Since" parameters

`GET  https://insight-api.eyenetra.com/api/v1/test_results?q=netra&sort=-uuid&updated_since="01-01-2016"`

You can also set "updated_since" or "created_since" parameters, specifying a bottom limit date or date/time to your requests

## Show

> Response Example 

````
{
  "test_result": {
    "id": 1,
    "longitude": null,
    "latitude": null,
    "uuid": null,
    "exam_date": null,
    "created_at": "2015-11-13T16:27:21.466Z",
    "updated_at": "2015-11-13T16:27:21.466Z",
    "distance_eyewear": "Constant wear glasses",
    "near_eyewear": "Constant wear glasses",
    "test_method": "Screening",
    "device_id": null,
    "app_version": null,
    "distance_binocular_id": 1,
    "near_binocular_id": 2,
    "notes": "This is the tag"
  }
}
````

### HTTP Request

`GET https://insight-api.eyenetra.com/api/v1/test_results/{:test_result_id}`

Obs.: To CSV exported data, add .csv as the format.
