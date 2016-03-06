# Entities

This demostrates our project enitites.

## User

Parameter | Type | Value | Notes
--------- | ---- | ----- | -----
id | int | todo | to do
url | | | 
name | | | 
image | | | 
about | |  `"about":{ "location":"Egypt", "Email":"ali@allam.com", "bio":null }` |
stats | |  `"stats":{ "projects":0, "contributions":5 }` |
projects | |  `http://api.lockscreen.com/v1/users/1411414/created_projects` |
contributions | |  `http://api.lockscreen.com/v1/users/1411414/contributions` |
createdAt | | 




## Project

Parameter | Type | Value | Notes
--------- | ---- | ----- | -----
id | int | todo | to do
url | | | 
name | | | 
image | | | 
owner | |`"owner":{ "id":11, "url":"http://api.lockscreen.com/v1/users/11", "name":"Galileo Galilei" }` | 
createdAt | | |
enrollmentsCount | | | 
contributionsCount | | |
isFeatured | | |
category | | `"category":{ "id":210, "url":"http://api.lockscreen.com/v1/categories/210", "name":"social" }`|
contributionType | | `"contributionType":{ "typeInputs":{ "available":false, "typeInputsNumber":null, "typeInputsText":null }` |
briefDescription | | | 
description | | | 
results | | | 
stats | | | 


## Category

Parameter | Type | Value | Notes
--------- | ---- | ----- | -----
id | int | todo | to do
url | | | 
name | | | 
image | | | 
description | | | 



## Contribution 

Parameter | Type | Value | Notes
--------- | ---- | ----- | -----
id | int | todo | to do
url | | | 
project | |`"project":{ "projectID":7898789, "url":"http://api.lockscreen.com/v1/projects/7898789", "name":"Say what you see", "image":"http://www.lockscreen.com/projects_images/1.jpg" }` | 
contributor | | | 
createdAt | | |
data | | |

