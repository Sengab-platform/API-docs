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
  "project_id": "project::3",
  "url": "http://api.sengab.com/v1/projects/project::3"
}
```

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
  "project_id": "project::3",
  "url": "http://api.sengab.com/v1/projects/project::3"
}
```
This endpoint withdraws a user from a project.

### HTTP Request

`DELETE http://api.sengab.com/v1/me/enrollments`

Parameter | Required
--------- | --------
project_id | YES
