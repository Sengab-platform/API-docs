# Contributions

## Submit a contribution in a project

```http
POST /me/submissions HTTP/1.1
Content-Type: application/json; charset=utf-8
Authorization: X-Auth-Token YOUR_ACCESS_TOKEN
```

> The above command returns JSON structured like this

```http
HTTP/1.1 201 Created
Content-Type: application/json
```
```json
{
    "id": "contribution::1::5",
    "url": "http://api.sengab.com/v1/contributions/contribution::1::5"
}
```

> The above response is for a contribution to project with `id` equals `project::1` submitted by user with `id` equals `user::5`

This endpoint submits a contribution to a project.

### HTTP Request

`POST http://api.sengab.com/v1/me/submissions`

### Request body:

Parameter              | Description                                                                                     | Required
---------------------- | ----------------------------------------------------------------------------------------------- | --------
user_gender             | Contributor's gender.                                                                         | YES
project_id              | Project ID.                                                                                  | YES
contribution           | Contribution object, see below.                                                              | YES
contribution.created_at | Date of contribution.                                                                           | YES
contribution.data      | Content of data will be different according to the project template, for more check Templates section. | YES
