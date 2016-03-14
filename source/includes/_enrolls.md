# - Enrollment

## Enroll in a project

```http
POST /users/<USER_ID>/enrolled-projects HTTP/1.1
Content-Type: application/json; charset=utf-8
Authorization: X-Auth-Token YOUR_ACCESS_TOKEN
```
> The above command returns JSON structured like this:

```http
HTTP/1.1 200 OK
Content-Type: application/json
```

```json
{
	"url": "http://api.lockscreen.com/v1/projects/156445",
	"projectId": 156445,
    "templateID":2,
    "templateBody": ""     
}
```

```java
 // templateBody differs according to the project template type
```

This endpoint enrolls a user in a project.

### HTTP Request

`POST http://api.lockscreen.com/v1/projects`

Parameter | Required
--------- | --------
projectId | YES

## Withdraw from project

```http
DELETE /users/<USER_ID>/enrolled-projects HTTP/1.1
Content-Type: application/json; charset=utf-8
Authorization: X-Auth-Token YOUR_ACCESS_TOKEN
```

> The above command returns JSON structured like this:

```http
HTTP/1.1 200 OK
Content-Type: application/json
```

```json
{
	"projectId": 454545
}
```
This endpoint withdraws a user from a project.

### HTTP Request

`DELETE http://api.lockscreen.com/v1/users/<USER_ID>/enrolled_projects`

Parameter | Description
--------- | -----------
projectId | The id of the project the user wants to withdraw from.