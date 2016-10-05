# Test Results

* [List](#list)
* [Show](#show)

The **Test Results** are the logic structure used to save the readings from Netra and Netrometer devices and, also, the customer's screening and contacts information.

#### Authentication

All requests require [authentication](ApiV1BasicAuthentication).

-----

## List

````
GET /api/v1/test_results/
````

### Example Request

````
https://dev-portal-api.eyenetra.com:7443/api/v1/test_results
````

Obs.: To CSV exported data, add .csv as the format.

### Example Response

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
      "right_image_id_1": null,
      "right_image_id_2": null,
      "right_image_id_3": null,
      "left_image_id_1": null,
      "left_image_id_2": null,
      "left_image_id_3": null,
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

### Filters

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

````
https://dev-portal-api.eyenetra.com:7443/api/v1/test_results?test_method=Netrometer
````

### Searching

You can use the param "q" (for query) to set a string that will be used to search alike entries (case insensitive, using SQL "LIKE" command) on the following columns:
* test_method
* distance_eyewear
* near_eyewear
* uuid
* exam_date
* device_id
* app_version
* notes (TAG)

````
https://dev-portal-api.eyenetra.com:7443/api/v1/test_results?q=netra
````

### Sorting

The same columns used for filtering can be used for sorting. To sort your request, you pass the column name on the parameter "sort":

````
https://dev-portal-api.eyenetra.com:7443/api/v1/test_results?sort=app_version
````

The default order when passing a parameter is ascending, you can change for descending passing a "-" before the column name:

````
https://dev-portal-api.eyenetra.com:7443/api/v1/test_results?sort=-app_version
````

The default sort for requests is "-updated_at".

### "Since" parameters

You can also set "updated_since" or "created_since" parameters, specifying a bottom limit date or date/time to your requests

````
https://dev-portal-api.eyenetra.com:7443/api/v1/test_results?q=netra&sort=-uuid&updated_since="01-01-2016"
````

-----

## Show

````
GET /api/v1/test_results/{:test_result_id}
````

### Example Request

````
https://dev-portal-api.eyenetra.com:7443/api/v1/test_results/1
````

Obs.: To CSV exported data, add .csv as the format.

### Example Response

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
    "right_image_id_1": null,
    "right_image_id_2": null,
    "right_image_id_3": null,
    "left_image_id_1": null,
    "left_image_id_2": null,
    "left_image_id_3": null,
    "device_id": null,
    "app_version": null,
    "distance_binocular_id": 1,
    "near_binocular_id": 2,
    "notes": "This is the tag"
  }
}
````
