# Categories

## List All Categories

```http
GET /categtories HTTP/1.1
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
	"categories": [{
		"id": 458,
		"name": "health",
		"img": "www.lookscreen.com/category_images/458.jpg",
		"url": "api.lookscreen.com/v1/categories/458",
		"desc": "This category contains all projects that related to heath"
	}, {
		"id": 584,
		"name": "science",
		"img": "www.lookscreen.com/category_images/584.jpg",
		"url": "api.lookscreen.com/v1/categories/584",
		"desc": "This category contains all projects that related to heath"

	}],
	"next_id": -1,
	"total": 2
}
```

This endpoint retrieves all categories.

### HTTP Request

`GET http://api.lockscreen.com/v1/categories`

<aside class="notice">
This action is paginated. See the pagination documentation for details.
</aside>

## List Projects of a Category

```http
GET /categtories/13 HTTP/1.1
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
	"id": "458",
	"name": "health",
	"img": "www.lookscreen.com/category_images/458_bg.jpg",
	"projects": [{
		"id": 13,
		"name": "Show me a pet",
		"url": "http://api.lockscreen.com/v1/projects/7",
		"thumbnail_url": "http://www.lockscreen.com/projects_thumbnails/7.jpg",
		"owner": {
			"id": 41,
			"name": "Albert Einstein",
			"url": "http://api.lockscreen.com/v1/users/41"
		},
		"created_at": "2008-01-14T04:33:35Z",
		"brief_description": "This a brief description about this project",
		"type": "photos",
		"isFeatured": true,
		"enrollment_count": 1730,
		"contributions_count": 1542,
		"goal": 4000,
		"progress": 38.55
	}],
	"next_id": -1,
	"total": 1
}
```
### HTTP Request

`GET http://api.lockscreen.com/v1/categories/<ID>`

<aside class="notice">
This action is paginated. See the pagination documentation for details.
</aside>
