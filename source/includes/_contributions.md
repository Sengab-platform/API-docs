# Contributions

## Add a contribution in a project

```http
POST /projects/<project-id>/results HTTP/1.1
Content-Type: application/json; charset=utf-8
Authorization: token YOUR_ACCESS_TOKEN
```

> The above command returns JSON structured like this:

```http
HTTP/1.1 201 Created
Content-Type: application/json
```

```json
{
	"href":"api.lookscreen.com/v1/projects/<project-id>/results/<contribution-id>"
}
```

This endpoint add a contribution to a project.

### HTTP Request

`POST http://api.lockscreen.com/v1/projects/<project-id>/results/`

Parameter | Required | Description
--------- | -------- | ------------
user_id | YES | TEMP; SHOULD BE DELETED
project_id | YES | The ID of the project
contribution | YES | Object of contribution (see below)
contribution.created_at | YES | Date of contribution
contribution.data | YES | Content of data will be different based on the project
contribution.data.first_name | - | -
contribution.data.last_name | - | -
