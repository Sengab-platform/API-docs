# Projects

## List all projects

```http
GET /projects HTTP/1.1
Content-Type: application/json; charset=utf-8
```

> The above command returns JSON structured like this:

```http
HTTP/1.1 206 Partial Content
Content-Type: application/json
```

```json
[
  {
    "id": "project::3",
    "name": "Project of template 3",
    "owner": {
      "id": "user::11",
      "url": "http://api.sengab.com/v1/users/user::11",
      "name": "Ahmad El-Melegy",
      "image": "https://lh3.googleusercontent.com/.../photo.jpg"
    },
    "url": "http://api.sengab.com/v1/projects/project::3",
    "goal": 2000,
    "image": "image",
    "template_id": 3,
    "created_at": "2016-02-12T03:21:55Z",
    "brief_description": "short",
    "enrollments_count": 0,
    "contributions_count": 17,
    "category": {
      "category_id": "category::3",
      "url": "http://api.sengab.com/v1/categories/category::3",
      "name": "sports"
    }
  },
  {
    "id": "project::2",
    "name": "Project of template 2",
    "owner": {
      "id": "user::11",
      "url": "http://api.sengab.com/v1/users/user::11",
      "name": "Ahmad El-Melegy",
      "image": "https://lh3.googleusercontent.com/.../photo.jpg"
    },
    "url": "http://api.sengab.com/v1/projects/project::2",
    "goal": 2000,
    "image": "image",
    "template_id": 2,
    "created_at": "2016-02-12T03:21:55Z",
    "brief_description": "short",
    "enrollments_count": 0,
    "contributions_count": 3,
    "category": {
      "category_id": "category::2",
      "url": "http://api.sengab.com/v1/categories/category::2",
      "name": "sports"
    }
  },
  {
    "id": "project::1",
    "name": "Project of template 1",
    "owner": {
      "id": "user::11",
      "url": "http://api.sengab.com/v1/users/user::11",
      "name": "Ahmad El-Melegy",
      "image": "https://lh3.googleusercontent.com/.../photo.jpg"
    },
    "url": "http://api.sengab.com/v1/projects/project::1",
    "goal": 2000,
    "image": "image",
    "template_id": 1,
    "created_at": "2016-02-12T03:21:55Z",
    "brief_description": "short",
    "enrollments_count": -2,
    "contributions_count": 3,
    "category": {
      "category_id": "category::1",
      "url": "http://api.sengab.com/v1/categories/category::1",
      "name": "health"
    }
  }
]
```

This endpoint retrieves all projects.

### HTTP Request

`GET http://api.sengab.com/v1/projects`

### Optional Parameters

Parameter | Type | Value
--------- | ---- | -----
filter | string | `popular` / `latest`

<aside class="notice">
This action is paginated. See the pagination documentation for details.
</aside>

## Get a specific project

```http
GET /projects/:id HTTP/1.1
Content-Type: application/json; charset=utf-8
```

> The above command returns JSON structured like this:

```http
HTTP/1.1 200 OK
Content-Type: application/json
```

```json
{
	"id": 7,
	"url": "http://api.sengab.com/v1/projects/7",
	"name": "Show me a pet",
	"image": "http://www.sengab.com/projects_images/7.jpg",
	"owner": {
		"id": 41,
		"url": "http://api.sengab.com/v1/users/41",
		"first_name": "Albert",
		"last_name": "Einstein",
		"image": "http://www.sengab.com/profiles_images/41.jpg"
	},
	"created_at": "2008-01-14T04:33:35Z",
	"brief_description": "This a brief description about this project",
	"detailed_description": "This is a detailed description about this project",
	"enrollments_count": 1730,
	"contributions_count": 1542,
	"template_id": 1,
	"category": {
		"id": 584,
		"url": "http://api.sengab.com/v1/categories/584",
		"name": "science"
	},
	"description": "Take a photo for any pet you",
	"results": "http://api.sengab.com/v1/projects/7/results",
	"stats": "http://api.sengab.com/v1/projects/7/stats"
}
```

This endpoint retrieves a specific project.

### HTTP Request

`GET http://api.sengab.com/v1/projects/<PROJECT_ID>`


## Get a project with template body

```http
GET /projects/:id?format="with_template_body" HTTP/1.1
Content-Type: application/json; charset=utf-8
```

> The above command returns JSON structured like this:

```http
HTTP/1.1 206 Partial Content
Content-Type: application/json
```

```json
{
  "id": "project::3",
  "name": "Project of template 3",
  "owner": {
    "id": "user::11",
    "url": "http://api.sengab.com/v1/users/user::11",
    "name": "Ahmad El-Melegy",
    "image": "https://lh3.googleusercontent.com/../photo.jpg"
  },
  "url": "http://api.sengab.com/v1/projects/project::3",
  "goal": 2000,
  "image": "image",
  "template_id": 3,
  "template_body": {
    "questions": [
      {
        "id": "1",
        "title": "what?"
      },
      {
        "id": "2",
        "title": "why?"
      }
    ]
  },
  "created_at": "2016-02-12T03:21:55Z",
  "brief_description": "short",
  "detailed_description": "detailed one",
  "enrollments_count": 25,
  "contributions_count": 17,
  "category": {
    "category_id": "category::3",
    "url": "http://api.sengab.com/v1/categories/category::3",
    "name": "sports"
  },
  "results": "result::3",
  "stats": "stats::3"
}
```

This endpoint retrieves a specific project with the template body.

### HTTP Request

`GET http://api.sengab.com/v1/projects/<PROJECT_ID>?format="with_template_body"`

### Required Parameter

Parameter | Type | Value
--------- | ---- | -----
format | string | `with_template_body`

## Add project

```http
POST /projects HTTP/1.1
Content-Type: application/json; charset=utf-8
Authorization: X-Auth-Token YOUR_ACCESS_TOKEN
```

```json
{
    "name": "Recognize image",
    "brief_description": "short",
    "detailed_description": "long",
    "goal": 500,
    "image": "fdfdfdfdfjdkfd4f5dfdf4df",
    "created_at": "2016-02-12T03:21:55Z",
    "category_id": "category::5",
    "template_id": 1,
    "templateBody": {}
}
```

This endpoint adds a new project.

### HTTP Request

`POST http://api.sengab.com/v1/projects`

### Request body

Parameter | Description
--------- | -----------
name |Project name
brief_description | Short project description.
detailed_description | Detailed project description.
goal | Project contributions count goal.
image | Project image.
created_at | Project creation date.
category_id | Id of project's category.
template_id | Defines the project template, for more check Templates section.
template_body | Defines the template body for a project. It differs according to template_id, for more check Templates section.


> The above command returns JSON structured like this

```http
HTTP/1.1 201 CREATED
Content-Type: application/json
```

```json
{
	"id": 4545454,
	"url": "http://www.sengab.com/projects/45454",
	"name": "Recognize Image",
	"image": "http://www.sengab.com/projects_thumbnails/15454545.jpg",
	"created_at": "2016-02-12T03:21:55Z"
}
```

## Search in projects

```http
GET /projects/search/recognize HTTP/1.1
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
    "id": "project::2",
    "name": "Project of template 2",
    "owner": {
      "id": "user::11",
      "url": "http://api.sengab.com/v1/users/user::11",
      "name": "Ahmad El-Melegy",
      "image": "https://lh3.googleusercontent.com/.../photo.jpg"
    },
    "url": "http://api.sengab.com/v1/projects/project::2",
    "goal": 2000,
    "image": "image",
    "template_id": 2,
    "created_at": "2016-02-12T03:21:55Z",
    "brief_description": "short",
    "enrollments_count": 7,
    "contributions_count": 3,
    "category": {
      "category_id": "category::2",
      "url": "http://api.sengab.com/v1/categories/category::2",
      "name": "sports"
    }
  }
]
```

This endpoint retrieves projects with titles including the value of the `search` query parameter.

### HTTP Request

`GET http://api.sengab.com/v1/projects/search/<keyword>`

### URL Parameters

Parameter | Description
--------- | -----------
keyword | The keyword that you search for in projects' titles.

<aside class="notice">
This action is paginated. See the pagination documentation for details.
</aside>

## List stats of a project

```http
GET /projects/<PROJECT_ID>/stats HTTP/1.1
Content-Type: application/json; charset=utf-8
```
> The above command returns JSON structured like this

```http
HTTP/1.1 200 OK
Content-Type: application/json
```

```json
{
	"goal": 900,
	"contributions_count": 721,
	"contributors_count": 685,
	"contributors_gender": {
		"males": 358,
		"females": 227,
		"unknown": 100
		}
}
```

This endpoint retrieves statistics of a project.

### HTTP Request

`GET http://api.sengab.com/v1/projects/<PROJECT_ID>/stats`

### Response body

Parameter | Description
--------- | -----------
goal | Project contributions count goal.
contributions_count | Contributions count of the project.
contributors_count | Contributors count of the project.
contributors_gender | Object of contributors gender.
contributors_gender.males | Male contributors count.
contributors_gender.females | Female contributors count.
contributors_gender.unknown | Unknown contributors count.



## List results of a project

```http
GET /projects/<PROJECT_ID>/results HTTP/1.1
Content-Type: application/json; charset=utf-8
```

> The above command returns various JSON structured, based on the project type

```http
HTTP/1.1 200 OK
Content-Type: application/json
```

```json
{
	"contributions_count":2210,
	"results":""
}
```

```
"results" field differs according to the project template
```
This endpoint retrieves results of a project.

### HTTP Request

`GET http://api.sengab.com/v1/projects/<PROJECT_ID>/results`

<aside class="notice">
This action is paginated. See the pagination documentation for details.
</aside>
