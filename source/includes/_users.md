# Users

## Get user profile

```http
GET /users/<ID>/activities HTTP/1.1
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
	"href": "api.lookscreen.com/v1/users/1411414",
	"id": 4545445,
	"name": "Ali Allam",
	"avatar": "www.lookscreen.com/profiles_images/1411414.jpg",
	"about": {
		"location": "Egypt",
		"Email": "ali@allam.com",
		"interests": ["art", "social", "science"],
		"bio": null
	},
	"profile_owner": true,
	"stats": {
		"projects": 0,
		"contributions": 5
	},
	"projects": {
		"href": "api.lookscreen.com/v1/users/1411414/created_projects"
	},
	"contributions": {
		"href": "api.lookscreen.com/v1/users/1411414/contributions"
	}
}
```

This endpoint retrieves user's profile.

### HTTP Request

`GET http://api.lockscreen.com/v1/users/<ID>/`

### URL Parameters

Parameter | Description
--------- | -----------
ID |ID of the user

## List User's Activity

```http
GET /users/<ID>/activities HTTP/1.1
Content-Type: application/json; charset=utf-8
Authorization: token YOUR_ACCESS_TOKEN
```

> The above command returns JSON structured like this:

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
			"thumbnail": "http://www.lookscreen.com/projects_thumbnails/15454545.jpg",
			"name": "Recognize",
			"href": "api.lookscreen.com/v1/projects/156445"
		},
		"created_at": "2016-02-12T03:21:55Z"
	}],
	"next_id": -1,
	"total": 1
}
```

This endpoint retrieves all user's activities.

### HTTP Request

`GET http://api.lockscreen.com/v1/users/<ID>/activities`

<aside class="notice">
This action is paginated. See the pagination documentation for details.
</aside>

## List all projects that the user enrolled in

```http
GET /users/<user-id>/enrolled-projects HTTP/1.1
Content-Type: application/json; charset=utf-8
Authorization: token YOUR_ACCESS_TOKEN
```
> The above command returns JSON structured like this:

```http
HTTP/1.1 206 Partial Content
Content-Type: application/json
```
```json
{
	"projects": [{
		"id": 1,
		"name": "Say what you see",
		"url": "http://api.lockscreen.com/v1/projects/1",
		"thumbnail_url": "http://www.lockscreen.com/projects_thumbnails/1.jpg",
		"owner": {
			"id": 11,
			"name": "Galileo Galilei",
			"url": "http://api.lockscreen.com/v1/users/11"
		},
		"created_at": "2008-01-14T04:33:35Z",
		"enrollment_count": 700,
		"contributions_count": 510,
		"category": {
			"id": 210,
			"name": "Visual",
			"url": "http://api.lockscreen.com/v1/categories/4"
		}
	}],
	"next_id": -1,
	"total": 1
}
```

This endpoint retrieves all projects that the user enrolled in.

### HTTP Request

`GET http://api.lockscreen.com/v1/users/<user-id>/enrolled-projects/`

<aside class="notice">
This action is paginated. See the pagination documentation for details.
</aside>
