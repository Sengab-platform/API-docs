# Enrollment

## Enroll in a project

```http
POST /users/<user-id>/enrolled-projects HTTP/1.1
Content-Type: application/json; charset=utf-8
Authorization: token YOUR_ACCESS_TOKEN
```
> The above command returns JSON structured like this:

```http
HTTP/1.1 200 OK
Content-Type: application/json
```

```json
{
	"href": "api.lookscreen.com/v1/projects/156445",
	"projectID": 156445
}
```

This endpoint enrolls a user in a project.

### HTTP Request

`GET http://api.lockscreen.com/v1/projects`

Parameter | Required
--------- | --------
project_id | YES

## Disroll user from a project

```http
DELETE /users/<user-id>/enrolled-projects HTTP/1.1
Content-Type: application/json; charset=utf-8
Authorization: token YOUR_ACCESS_TOKEN
```

> The above command returns JSON structured like this:

```http
HTTP/1.1 200 OK
Content-Type: application/json
```

```json
{
	"project_id": 454545
}
```
This endpoint enrolls a user in a project.

### HTTP Request

`DELETE http://api.lockscreen.com/v1/users/<user-id>/enrolled-projects`

Parameter | Description
--------- | -----------
project_id | The id of the project to be deleted.
