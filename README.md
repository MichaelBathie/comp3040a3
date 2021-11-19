# Daily Dose of Covid

## Description
**Daily Dose of Covid** is a free online tool that provides users with information about recent COVID statistics in Manitoba. Users will be able to specify the location and date (or range of dates) when searching for information.

## Endpoints
### **GET/today**  
Shows the last COVID report for the specified location in Manitoba, or for all of Manitoba if unspecified.
Parameters:  
- location (string): An area in Manitoba. If not specified, the response will include COVID statistics for all of Manitoba.  
### **GET/history**  
Shows cumulative data from COVID reports within a specific date range for the specified location in Manitoba. If no dates are specified, it will show the entire history of COVID reports.
Parameters:  
- location (string): An area in Manitoba. If not specified, the response will include COVID statistics for all of Manitoba.
- date (string): Date in YYYY-MM-DD format. The response will include COVID statistics for this date.
- endDate (string): Date in YYYY-MM-DD format. This field is optional. If specified, the response will include COVID statistics between the _date_ parameter and the _endDate_ parameter.

## Sample Requests

#### Sample request:
```
https://dailydoseofcovid.ca/daily?date=2021-08-01&enddate=2021-08-30&location=winnipeg
```

#### Sample reponse:
```
{
    "results":
    {
      "new_cases": 11563,
      "deaths": 1065,
      "recovered": 12746,
    },
    "status":"OK"
}
```

## Resources

