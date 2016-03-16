# Users

## Get user profile

```http
GET /users/<ID>/activities HTTP/1.1
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
	"name": "Ali Allam",
	"image": "http://www.sengab.com/profiles_images/1411414.jpg",
	"about": {
		"location": "Egypt",
		"Email": "ali@allam.com",
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
{
	"activities": [{
		"id": "125",
		"project": {
			"id": 56565,
			"image": "http://www.sengab.com/projects_images/15454545.jpg",
			"name": "Recognize",
			"url": "http://api.sengab.com/v1/projects/56565"
		},
		"created_at": "2016-02-12T03:21:55Z"
	}],
	"next_id": -1,
	"total": 1
}
```

This endpoint retrieves all user's activities.

### HTTP Request

`GET http://api.sengab.com/v1/users/<ID>/activities`

<aside class="notice">
This action is paginated. Check the pagination documentation for details.
</aside>

## List all projects that the user enrolled in

```http
GET /users/<user-id>/enrolled_projects HTTP/1.1
Content-Type: application/json; charset=utf-8
```
> The above command returns JSON structured like this

```http
HTTP/1.1 206 Partial Content
Content-Type: application/json
```
```json
{
	"projects": [{
		"id": 1,
		"name": "Say what you see",
		"url": "http://api.sengab.com/v1/projects/1",
		"image": "http://www.sengab.com/projects_images/1.jpg",
		"owner": {
			"id": 11,
			"name": "Galileo Galilei",
			"url": "http://api.sengab.com/v1/users/11"
		},
		"created_at": "2008-01-14T04:33:35Z",
		"brief_description": "This a brief description about this project",
		"enrollment_count": 700,
		"contributions_count": 510,
		"is_featured": false,
    "template_id": 3,
		"category": {
			"id": 210,
			"name": "Visual",
			"url": "http://api.sengab.com/v1/categories/4"
		}
	}],
	"next_id": -1,
	"total": 1
}
```

## List projects created by a specific user

```http
GET /users/<user-id>/created-projects HTTP/1.1
Content-Type: application/json; charset=utf-8
```

> The above command returns JSON structured like this

```http
HTTP/1.1 206 Partial Content
Content-Type: application/json
```

```json
{
	"projects": [{
		"id": 1,
		"name": "Say what you see",
		"url": "http://api.sengab.com/v1/projects/1",
		"image": "http://www.sengab.com/projects_images/1.jpg",
		"brief_description": "This a brief description about this project",
		"created_at": "2008-01-14T04:33:35Z",
		"enrollment_count": 700,
		"contributions_count": 510,
		"is_featured": true,
    "template_id": 3,
		"category": {
			"id": 210,
			"name": "Visual",
			"url": "http://api.sengab.com/v1/categories/4"
		},
		"owner": {
			"id": 41,
			"name": "Albert Einstein",
			"url": "http://api.sengab.com/v1/users/41"
		}
	}]
}
```

This endpoint retrieves all projects that the user enrolled in.

### HTTP Request

`GET http://api.sengab.com/v1/users/<user-id>/enrolled_projects/`

<aside class="notice">
This action is paginated. Check the pagination documentation for details.
</aside>
