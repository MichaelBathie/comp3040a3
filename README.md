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
- date (string): Date in YYYY-MM-DD format. The response will include COVID statistics for just this date if no end date is specified.
- end_date (string): Date in YYYY-MM-DD format. This field is optional. If specified, the response will include COVID statistics between the *date* parameter and the *end_date* parameter.

## Sample Requests

#### Sample #1 
Request:  
```
https://dailydoseofcovid.ca/history?date=2021-08-01&enddate=2021-08-30&location=winnipeg
```
Response:  
```
{
    "location":"Winnipeg",
    "date":"2021-08-01",
    "end_date":"2021-08-30",
    "results":
    {
        "new_cases": 11563,
        "deaths": 1065,
        "recovered": 12746,
    },
    "status":"OK"
}
```

#### Sample #2:
Request:
```
https://dailydoseofcovid.ca/today?location=brandon
```
Response:
```
{
    "location":"Brandon",
    "results":
    {
        "new_cases": 97821,
        "deaths": 500,
        "recovered": 1237,
    },
    "status":"OK"
}
```
#### Sample #3: Invalid location
Request:
```
https://dailydoseofcovid.ca/today?location=tokyo
```
Response:
```
{
    "location":"Tokyo",
    "results": {},
    "status":"INVALID_LOCATION"
}
```
#### Sample #4: Invalid date
Request:
```
https://dailydoseofcovid.ca/history?date=2021-08-01&enddate=2023-01-01
```
Response:
```
{
    "location":"Manitoba",
    "date":"2021-08-01",
    "end_date":"2023-01-01",
    "results": {}
    "status":"INVALID_DATE"
}
```

## Status codes
- "OK": No errors occurred.
- "INVALID_LOCATION": The location parameter is missing or invalid.
- "INVALID_DATE": The date parameter is missing or invalid.
- "ERROR": Some other unknown error occured, likely a server error.
