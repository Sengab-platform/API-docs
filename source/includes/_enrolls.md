# Enrollment

## Enroll in a project

```http
POST /me/enrollments/ HTTP/1.1
Content-Type: application/json; charset=utf-8
Authorization: X-Auth-Token YOUR_ACCESS_TOKEN
```
> The above command returns JSON structured like this

```http
HTTP/1.1 200 OK
Content-Type: application/json
```

```json
{
	"url": "http://api.sengab.com/v1/projects/156445",
	"project_id": 156445,
    "template_id":2,
    "template_body": ""
}
```

> NOTE : "template_body" differs according to the project template type

This endpoint enrolls a user in a project.

### HTTP Request

`POST http://api.sengab.com/v1/me/enrollments`

Parameter | Required
--------- | --------
project_id | YES

## Withdraw from project

```http
DELETE /me/enrollments HTTP/1.1
Content-Type: application/json; charset=utf-8
Authorization: X-Auth-Token YOUR_ACCESS_TOKEN
```

> The above command returns JSON structured like this

```http
HTTP/1.1 200 OK
Content-Type: application/json
```

```json
{
	"project_id": 454545
}
```
This endpoint withdraws a user from a project.

### HTTP Request

`DELETE http://api.sengab.com/v1/me/enrollments`

Parameter | Description
--------- | -----------
project_id | The id of the project the user wants to withdraw from.
