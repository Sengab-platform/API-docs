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
	"url":"http://api.sengab.com/v1/projects/<PROJECT_ID>/results/<CONTRIBUTION_ID>"
}
```

This endpoint submits a contribution to a project.

### HTTP Request

`POST http://api.sengab.com/v1/me/submissions`

### Request body:

Parameter              | Description                                                                   | Required
---------------------- | ----------------------------------------------------------------------------------------------- | --------
user_gender             | Contributor's gender.                                                                         | YES
project_id              | Project ID.                                                                                  | YES
contribution           | Contribution object, see below.                                                              | YES
created_at | Date of contribution.                                                                           | YES
data      | Content of data will be different according to the project template, for more check Templates section. | YES
