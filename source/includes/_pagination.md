# Pagination
Most methods in the API accept the offset and limit parameters for fetching specific pages of results from the API.
Offset refers to starts at and defaults to 1, limit can be any value between 0 and 100 and defaults to 10.

### Parameters			
Name  | Type  |  Required | Description   
------|-------|-----------|------------
offset  | Number  | No  | The offset of the first record returned. Default is 0.
limit | Number  |  No | 	The number of records returned. Default is 10
