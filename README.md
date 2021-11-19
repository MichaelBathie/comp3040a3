# Daily Dose of Covid

## Description
**Daily Dose of Covid** is a free online tool that provides users with information about recent COVID statistics in Manitoba. Users will be able to specify the location and date (or range of dates) when searching for information.

## Endpoints
### **GET/daily**  
Parameters:  
- location (string): An area in Winnipeg. If not specified, the response will include COVID statistics for all of Manitoba.
- date (string): Date in YYYY-MM-DD format. The response will include COVID statistics for this date.
- endDate (string): Date in YYYY-MM-DD format. This field is optional. If specified, the response will include COVID statistics between the _date_ parameter and the _endDate_ parameter.
### **GET/total**  
Parameters:  
- location (string): An area in Winnipeg. If not specified, the response will include COVID statistics for all of Manitoba.  

## Sample Requests
- https://dailydoseofcovid.ca/daily?date=2021-08-01&enddate=2021-08-30&location=winnipeg

## Resources

## Sample Requests
