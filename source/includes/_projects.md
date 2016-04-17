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
{
  "projects": [
    {
      "id": 1,
      "url": "http://api.sengab.com/v1/projects/1",
      "name": "Say what you see",
      "image": "http://www.sengab.com/projects_images/1.jpg",
      "owner": {
        "id": 11,
        "url": "http://api.sengab.com/v1/users/11",
        "name": "Galileo Galilei",
        "image": "http://www.sengab.com/profiles_images/78951.jpg"
      },
      "created_at": "2008-01-14T04:33:35Z",
      "brief_description": "This a brief description about this project",
      "enrollments_count": 700,
      "contributions_count": 510,
      "goal": 500,
      "is_featured": true,
      "template_id": 1,
      "category": {
        "category_id": 210,
        "url": "http://api.sengab.com/v1/categories/210",
        "name": "social"
      }
    },
    {
      "id": 1,
      "url": "http://api.sengab.com/v1/projects/1",
      "name": "Say what you see",
      "image": "http://www.sengab.com/projects_images/1.jpg",
      "owner": {
        "id": 11,
        "url": "http://api.sengab.com/v1/users/11",
        "name": "Galileo Galilei",
        "image": "http://www.sengab.com/profiles_images/78951.jpg"
      },
      "created_at": "2008-01-14T04:33:35Z",
      "brief_description": "This a brief description about this project",
      "enrollments_count": 700,
      "contributions_count": 510,
      "goal": 500,
      "is_featured": true,
      "template_id": 1,
      "category": {
        "category_id": 210,
        "url": "http://api.sengab.com/v1/categories/210",
        "name": "social"
      }
    }
  ]
}
```

This endpoint retrieves all projects.

### HTTP Request

`GET http://api.sengab.com/v1/projects`

### Optional Parameters

Parameter | Type | Value
--------- | ---- | -----
filter | string | `popular` / `latest` / `featured`

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
  "id": "project::ac50cddd",
  "url": "http://api.sengab.com/v1/projects/project::ac50cddd",
  "name": "Show me a pet",
  "image": "http://www.sengab.com/projects_images/7.jpg",
  "owner": {
    "id": 41,
    "url": "http://api.sengab.com/v1/users/41",
    "name": "Albert Einstein",
    "image": "http://www.sengab.com/profiles_images/41.jpg"
  },
  "created_at": "2008-01-14T04:33:35Z",
  "brief_description": "This a brief description about this project",
  "detailed_description": "This is a detailed description about this project",
  "enrollments_count": 1730,
  "contributions_count": 1542,
  "is_featured": true,
  "template_id": 1,
  "goal": 500,
  "category": {
    "id": 584,
    "url": "http://api.sengab.com/v1/categories/category::a584",
    "name": "science"
  },
  "results": "http://api.sengab.com/v1/projects/project::ac50cddd/results",
  "stats": "http://api.sengab.com/v1/projects/project::ac50cddd/stats"
}
```

This endpoint retrieves a specific project.

### HTTP Request

`GET http://api.sengab.com/v1/projects/<PROJECT_ID>`

## Add project

```http
POST /projects HTTP/1.1
Content-Type: application/json; charset=utf-8
Authorization: X-Auth-Token YOUR_ACCESS_TOKEN
```

```json
{
  "name": "Recognize image",
  "brief_description": "Lorem Ipsum is simply dummy text of the printing and typesetting industry",
  "detailed_description": "Lorem Ipsum has been the industry's standard dummy text ever since the 1500s",
  "template_id": 1,
  "template_body": {},
  "goal": 5000,
  "is_featured": true,
  "image": "R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7",
  "category_id": 1,
  "created_at": "1997-07-16T19:20:30+01:00"
}
```

This endpoint adds a new project.

### HTTP Request

`POST http://api.sengab.com/v1/projects`

### Request body

Parameter | Description
--------- | -----------
name |project name
brief_description | Short project description.
detailed_description | Detailed project description.
goal | Project contributions count goal.
template_id | Defines the project template, for more check Templates section.
template_body | Defines the template body for a project. It differs according to template_id, for more check Templates section.
goal | The number of contributions that is needed to the projects.
image | Image of the project.
category_id | Defines category id that project belongs to
created_at | Project creation time


> The above command returns JSON structured like this

```http
HTTP/1.1 201 CREATED
Content-Type: application/json
```

```json
{
	"id": "project::43fx",
	"url": "http://www.sengab.com/projects/project::43fx",
	"name": "Recognize Image",
	"image": "http://www.sengab.com/projects_thumbnails/15.jpg",
	"created_at": "2016-02-12T03:21:55Z"
}
```

## Search in projects

```http
GET /projects/search/recognize HTTP/1.1
Content-Type: application/json; charset=utf-8
```
> The above command returns JSON structured like this:

```http
HTTP/1.1 206 Partial Content
Content-Type: application/json
```

```json
{
  "projects": [
    {
      "id": 1,
      "url": "http://api.sengab.com/v1/projects/1",
      "name": "Say what you see",
      "image": "http://www.sengab.com/projects_images/1.jpg",
      "owner": {
        "id": 11,
        "url": "http://api.sengab.com/v1/users/11",
        "name": "Galileo Galilei",
        "image": "http://www.sengab.com/profiles_images/78951.jpg"
      },
      "created_at": "2008-01-14T04:33:35Z",
      "brief_description": "This a brief description about this project",
      "enrollments_count": 700,
      "contributions_count": 510,
      "goal": 500,
      "is_featured": true,
      "template_id": 1,
      "category": {
        "category_id": 210,
        "url": "http://api.sengab.com/v1/categories/210",
        "name": "social"
      }
    },
    {
      "id": 1,
      "url": "http://api.sengab.com/v1/projects/1",
      "name": "Say what you see",
      "image": "http://www.sengab.com/projects_images/1.jpg",
      "owner": {
        "id": 11,
        "url": "http://api.sengab.com/v1/users/11",
        "name": "Galileo Galilei",
        "image": "http://www.sengab.com/profiles_images/78951.jpg"
      },
      "created_at": "2008-01-14T04:33:35Z",
      "brief_description": "This a brief description about this project",
      "enrollments_count": 700,
      "contributions_count": 510,
      "goal": 500,
      "is_featured": true,
      "template_id": 1,
      "category": {
        "category_id": 210,
        "url": "http://api.sengab.com/v1/categories/210",
        "name": "social"
      }
    }
  ]
}
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
GET /projects/<ID>/stats HTTP/1.1
Content-Type: application/json; charset=utf-8
```

> The above command returns various JSON structured, based on the project type

```http
HTTP/1.1 200 OK
Content-Type: application/json
```

```json
{
  "enrollments_count": 4866,
  "contributions_count": 1343,
  "contributors_gender": {
    "male": 1000,
    "female": 340,
    "unknown": 3
  }
}
```

This endpoint retrieves the stats of a project.

### HTTP Request

`GET http://api.sengab.com/v1/projects/<PROJECT_ID>/stats`

## List results of a project

```http
GET /projects/<ID>/results HTTP/1.1
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
This endpoint retrieves the contributions in a project.

### HTTP Request

`GET http://api.sengab.com/v1/projects/<PROJECT_ID>/results`

<aside class="notice">
This action is paginated. See the pagination documentation for details.
</aside>
