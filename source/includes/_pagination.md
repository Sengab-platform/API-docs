# Pagination
Most methods in the API accept the offset and limit parameters for fetching specific pages of results from the API.
Offset refers to starts at and defaults to 1, limit can be any value between 0 and 100 and defaults to 10.

### Parameters			
Name  | Type  |  Required | Description   
------|-------|-----------|------------
offset  | Number  | No  | The offset of the first record returned. Default is 0.
limit | Number  |  No | 	The number of records returned. Default is 10


The API response will include the total number of records that match this query as well as the ID of the next record.

### Response Fields
Name | Type | Description
-----|-------|-----------
total |	Number | The total number of available records.
next_id | Number | The id of the next record that match this query, if there is no next record, this will be -1.
