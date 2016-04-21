# Users

## Get user profile

```http
GET /users/<ID> HTTP/1.1
Content-Type: application/json; charset=utf-8
```

> The above command returns JSON structured like this

```http
HTTP/1.1 200 OK
Content-Type: application/json
```

```json
{
	"id": 4545445,
	"url": "http://api.sengab.com/v1/users/1411414",
	"first_name": "Ali",
	"last_name": "Allam",
	"image": "http://www.sengab.com/profiles_images/1411414.jpg",
	"about": {
		"location": "Egypt",
		"email": "ali@allam.com",
		"bio": null
	},
	"stats": {
		"projects": 0,
		"contributions": 5
	},
	"projects": "http://api.sengab.com/v1/users/1411414/created_projects",
	"contributions": "http://api.sengab.com/v1/users/1411414/contributions"
}
```

This endpoint retrieves user's profile.

### HTTP Request

`GET http://api.sengab.com/v1/users/<USER_ID>`

## List User's Activity

```http
GET /users/<USER_ID>/activities HTTP/1.1
Content-Type: application/json; charset=utf-8
```

> The above command returns JSON structured like this

```http
HTTP/1.1 206 Partial Content
Content-Type: application/json
```

```json
[{
		"id": "activity::125",
		"project": {
			"id": "project::56565",
			"image": "http://www.sengab.com/projects_images/15454545.jpg",
			"name": "Recognize",
			"url": "http://api.sengab.com/v1/projects/project::56565"
		},
		"created_at": "2016-02-12T03:21:55Z"
	}]
```

This endpoint retrieves all user's activities.

### HTTP Request

`GET http://api.sengab.com/v1/users/<ID>/activities`

<aside class="notice">
This action is paginated. Check the pagination documentation for details.
</aside>

## List enrolled projects

```http
GET /users/<USER_ID>/enrolled_projects HTTP/1.1
Content-Type: application/json; charset=utf-8
```
> The above command returns JSON structured like this

```http
HTTP/1.1 206 Partial Content
Content-Type: application/json
```

```json
[
  {
    "id": "project::5",
    "name": "Say what you see",
    "url": "http://api.sengab.com/v1/projects/project::5",
    "image": "http://www.sengab.com/projects_images/1.jpg",
    "owner": {
      "id": "user::8",
      "name": "Amr El-Masry",
      "url": "http://api.sengab.com/v1/users/user::8",
      "image": "http://Sengab.com/users_images/user_5.png"
    },
    "created_at": "2008-01-14T04:33:35Z",
    "brief_description": "This a brief description about this project",
    "enrollments_count": 700,
    "contributions_count": 510,
    "is_featured": false,
    "template_id": 3,
    "category": {
      "id": "category::2",
      "name": "Visual",
      "url": "http://api.sengab.com/v1/categories/category::2"
    }
  }
]
```
This endpoint retrieves all projects that the user enrolled in.

### HTTP Request

`GET http://api.sengab.com/v1/users/<USER_ID>/enrolled_projects/`

<aside class="notice">
This action is paginated. Check the pagination documentation for details.
</aside>

## List created projects

```http
GET /users/<user-id>/created_projects HTTP/1.1
Content-Type: application/json; charset=utf-8
```

> The above command returns JSON structured like this

```http
HTTP/1.1 206 Partial Content
Content-Type: application/json
```
```json
[
  {
    "id": "project::5",
    "name": "Say what you see",
    "url": "http://api.sengab.com/v1/projects/project::5",
    "image": "http://www.sengab.com/projects_images/1.jpg",
    "owner": {
      "id": "user::8",
      "name": "Amr El-Masry",
      "url": "http://api.sengab.com/v1/users/user::8",
      "image": "http://Sengab.com/users_images/user_5.png"
    },
    "created_at": "2008-01-14T04:33:35Z",
    "brief_description": "This a brief description about this project",
    "enrollments_count": 700,
    "contributions_count": 510,
    "is_featured": false,
    "template_id": 3,
    "category": {
      "id": "category::2",
      "name": "Visual",
      "url": "http://api.sengab.com/v1/categories/category::2"
    }
  }
]
```

This endpoint retrieves all projects created by the user.

### HTTP Request

`GET http://api.sengab.com/v1/users/<USER_ID>/created_projects/`

<aside class="notice">
This action is paginated. Check the pagination documentation for details.
</aside>
