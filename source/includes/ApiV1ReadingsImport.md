# Readings Import

The **Readings Import** endpoint is used to save readings directly to insight database, without the necessity of a TeleRx flow import. It's used to save the stand-alone, tabletless version of Netra and for Netrometer readings.

<aside class="warn">
All requests require <a href="#basic-authentication">authentication</a>.
</aside>

## Create

### HTTP Request

`POST /api/v1/readings_import/`

> https://dev-portal-api.eyenetra.com:7443/api/v1/readings_import/

````
{
  "readings": {
    "exam_date": "Wed Oct 28 14:38:03 EDT 2015",
    "longitude": -71.07596,
    "latitude": 42.37838,
    "app_version": "0.5.1",
    "device_id": -1,
    "test_method": "Netrometer",
    "results": {
      "distance_type": "Distance",
      "pd": 62,
      "va": 0.8,
      "right_eye": {
        "sphere": -0.75,
        "cylinder": -0.25,
        "axis": 165,
        "add": 0,
        "confidence": 0.1,
        "eye": "Right"
      },
      "left_eye": {
        "sphere": 1,
        "cylinder": -0.25,
        "axis": 130,
        "add": 0,
        "confidence": 0.1,
        "eye": "Left"
      }
    },
    "adj_results": {
      "distance_type": "Distance",
      "pd": 60,
      "va": 0.666,
      "right_eye": {
        "sphere": -0.75,
        "cylinder": 0,
        "axis": 170,
        "add": 0,
        "confidence": 0.1,
        "eye": "Right"
      },
      "left_eye": {
        "sphere": 1.25,
        "cylinder": 0,
        "axis": 180,
        "add": 0.5,
        "confidence": 0.1,
        "eye": "Left"
      }
    }
  }
}
````

````
{
  "info": "Success",
  "test_result_id": 20997
}
````
