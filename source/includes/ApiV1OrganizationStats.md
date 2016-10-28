# Organization Stats

> Organization Stats Structure Example

````
{
  "organization_stats": {
    "test_results": {"...":"..."},
    "visits": {"...":"..."},
    "customers": {"...":"..."},
    "graph_readings": {
      "by_year": {"...":"..."},
      "netra_by_year": {"...":"..."},
      "netrometer_by_year": {"...":"..."},
      "by_month": {"...":"..."},
      "netra_by_month": {"...":"..."},
      "netrometer_by_month": {"...":"..."},
      "by_day": {"...":"..."},
      "netra_by_day": {"...":"..."},
      "netrometer_by_day": {"...":"..."}
    }
  }
}
````

List of **Organization Stats** of the requester organization, as visits, customers and test results counts.

The graph information is optimized to be used with  [Chart.js](http://www.chartjs.org/).

<aside class="warn">
All requests require <a href="#basic-authentication">authentication</a>.
</aside>

## List

> Response Example 

````
{
  "organization_stats": {
    "test_results": {
      "count": 26383,
      "netrometer": 13187,
      "netra": 13187,
      "custom": 9
    },
    "visits": {
      "count": 15459,
      "incomplete": 4187,
      "completed": 4454,
      "new": 6818
    },
    "customers": {
      "count": 16132,
      "prescribed": 1351,
      "passed": 1400,
      "referred": 1396
    },
    "graph_readings": {
      "by_year": {
        "dates": ["2012", "2013", "2014", "2015", "2016"],
        "counts": [0, 0, 0, 0, 26374]
      },
      "netra_by_year": {
        "dates": ["2012", "2013", "2014", "2015", "2016"],
        "counts": [0, 0, 0, 0, 13187]
      },
      "netrometer_by_year": {
        "dates": ["2012", "2013", "2014", "2015", "2016"],
        "counts": [0, 0, 0, 0, 13187]
      },
      "by_month": {
        "dates": ["2015-12", "2016-01", "2016-02", "2016-03", "2016-04", "2016-05", "2016-06", "2016-07", "2016-08", "2016-09"],
        "counts": [0, 0, 0, 0, 0, 0, 4840, 7421, 6165, 7948]
      },
      "netra_by_month": {
        "dates": ["2015-12", "2016-01", "2016-02", "2016-03", "2016-04", "2016-05", "2016-06", "2016-07", "2016-08", "2016-09"],
        "counts": [0, 0, 0, 0, 0, 0, 2420, 3710, 3083, 3974]
      },
      "netrometer_by_month": {
        "dates": ["2015-12", "2016-01", "2016-02", "2016-03", "2016-04", "2016-05", "2016-06", "2016-07", "2016-08", "2016-09"],
        "counts": [0, 0, 0, 0, 0, 0, 2420, 3711, 3082, 3974]
      },
      "by_day": {
        "dates": ["2016-09-20", "2016-09-21", "2016-09-22", "2016-09-23", "2016-09-24", "2016-09-25", "2016-09-26", "2016-09-27", "2016-09-28", "2016-09-29"],
        "counts": [226, 658, 366, 322, 0, 0, 488, 196, 352, 246]
      },
      "netra_by_day": {
        "dates": ["2016-09-20", "2016-09-21", "2016-09-22", "2016-09-23", "2016-09-24", "2016-09-25", "2016-09-26", "2016-09-27", "2016-09-28", "2016-09-29"],
        "counts": [113, 329, 183, 161, 0, 0, 244, 98, 176, 123]
      },
      "netrometer_by_day": {
        "dates": ["2016-09-20", "2016-09-21", "2016-09-22", "2016-09-23", "2016-09-24", "2016-09-25", "2016-09-26", "2016-09-27", "2016-09-28", "2016-09-29"],
        "counts": [113, 329, 183, 161, 0, 0, 244, 98, 176, 123]
      }
    }
  }
}
````

The request information is very basic. The target organization will be defined by the logged user requester.

### HTTP Request

`GET https://insight-api.eyenetra.com/api/v1/organization_stats/`

