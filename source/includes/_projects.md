# - Projects

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
  "projects":[  
    {  
      "id":1,
      "url":"http://api.lockscreen.com/v1/projects/1",
      "name":"Say what you see",
      "image":"http://www.lockscreen.com/projects_images/1.jpg",
      "owner":{  
        "id":11,
        "url":"http://api.lockscreen.com/v1/users/11",
        "name":"Galileo Galilei"
      },
      "createdAt":"2008-01-14T04:33:35Z",
      "briefDescription":"This a brief description about this project",
      "enrollmentsCount":700,
      "contributionsCount":510,
      "isFeatured":true,
      "templateID": 1,
      "category":{  
        "id":210,
        "url":"http://api.lockscreen.com/v1/categories/210",
        "name":"social"
      }
    },
    {  
      "id":7,
      "name":"Show me a pet",
      "url":"http://api.lockscreen.com/v1/projects/7",
      "image":"http://www.lockscreen.com/projects_images/7.jpg",
      "owner":{  
        "id":41,
        "url":"http://api.lockscreen.com/v1/users/41",
        "name":"Albert Einstein"
      },
      "createdAt":"2008-01-14T04:33:35Z",
      "briefDescription":"This a brief description about this project",
      "enrollmentsCount":1730,
      "contributionsCount":1542,
      "goal":4000,
      "progress":38.55,
      "isFeatured":true,
      "templateID": 2,
      "category":{  
        "id":584,
        "url":"http://api.lockscreen.com/v1/categories/584",
        "name":"science"
      }
    }
  ],
  "nextId":-1,
  "total":2
}
```

This endpoint retrieves all projects.

### HTTP Request

`GET http://api.lockscreen.com/v1/projects`

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
  "id":7,
  "url":"http://api.lockscreen.com/v1/projects/7",
  "name":"Show me a pet",
  "image":"http://www.lockscreen.com/projects_images/7.jpg",
  "owner":{  
    "id":41,
    "url":"http://api.lockscreen.com/v1/users/41",
    "name":"Albert Einstein",
    "image":"http://www.lockscreen.com/profiles_images/41.jpg"
  },
  "createdAt":"2008-01-14T04:33:35Z",
  "briefDescription":"This a brief description about this project",
  "detailedDescription":"This is a detailed description about this project",
  "enrollmentsCount":1730,
  "contributionsCount":1542,
  "isFeatured":true,
  "templateID": 1,
  "category":{  
    "id":584,
    "url":"http://api.lockscreen.com/v1/categories/584",
    "name":"science"
  },
  "description":"Take a photo for any pet you",
  "results":"http://api.lockscreen.com/v1/projects/7/results",
  "stats":"http://api.lockscreen.com/v1/projects/7/stats"
}
```

This endpoint retrieves a specific project.

### HTTP Request

`GET http://api.lockscreen.com/v1/projects/<PROJECT_ID>`

## Add project

```http
POST /projects HTTP/1.1
Content-Type: application/json; charset=utf-8
Authorization: X-Auth-Token YOUR_ACCESS_TOKEN
```

```json
{  
  "name":"Recognize image",
  "briefDescription":"Lorem Ipsum is simply dummy text of the printing and typesetting industry",
  "detailedDescription":"Lorem Ipsum has been the industry's standard dummy text ever since the 1500s",
  "templateID": 1,
  "questions":{
    "text1": "Where are you from ?",
    "image1":"Add a photo of your city"
  },
  "goal":5000,
}
```

This endpoint adds a new project.

### HTTP Request

`POST http://api.lockscreen.com/v1/projects`

### Request body

Parameter | Description
--------- | -----------
name |project name
briefDescription | short project description
detailedDescription | detailed project description
goal | project contributions count goal
contributionType | defines the type of contribution for a project


> The above command returns JSON structured like this:

```http
HTTP/1.1 201 CREATED
Content-Type: application/json
```

```json
{  
  "id":4545454,
  "url":"http://www.lockscreen.com/projects/45454",
  "name":"Recognize Image",
	"image":"http://www.lockscreen.com/projects_thumbnails/15454545.jpg",
  "createdAt":"2016-02-12T03:21:55Z"
}
```

## Search in projects

```http
GET /projects?search="pet" HTTP/1.1
Content-Type: application/json; charset=utf-8
```
> The above command returns JSON structured like this:

```http
HTTP/1.1 206 Partial Content
Content-Type: application/json
```

```json
{  
  "projects":[  
    {  
      "id":7,
      "url":"http://api.lockscreen.com/v1/projects/7",
      "name":"Show me a pet",
      "image":"http://www.lockscreen.com/projects_imags/7.jpg",
      "owner":{  
        "id":41,
        "url":"http://api.lockscreen.com/v1/users/41",
        "name":"Albert Einstein"
      },
      "createdAt":"2008-01-14T04:33:35Z",
      "briefDescription":"This a brief description about this project",
      "enrollmentsCount":1730,
      "contributionsCount":1542,
      "isFeatured":true,
      "templateID": 1,
      "category":{  
        "id":584,
        "url":"http://api.lockscreen.com/v1/categories/584",
        "name":"science"
      }
    }
  ],
  "nextId":-1,
  "total":1
}
```

This endpoint retrieves projects with titles including the value of the `search` query parameter.

### HTTP Request

`GET http://api.lockscreen.com/v1/projects/search?<keyword>`

### URL Parameters

Parameter | Description
--------- | -----------
keyword | The keyword that you search for in projects' titles.

<aside class="notice">
This action is paginated. See the pagination documentation for details.
</aside>


## List results of a project

```http
GET /projects/<ID>/results HTTP/1.1
Content-Type: application/json; charset=utf-8
```

> The above command returns various JSON structured, based on the project type
e.g if the project collects images the like this:

```http
HTTP/1.1 200 OK
Content-Type: application/json
```

```json
{
	"contributions" : [
		{
			"ID":47878,
			"url":"http://api.lockscreen.com/v1/contributions/47878",
			"project":{
				"projectID":7898789,
				"url":"http://api.lockscreen.com/v1/projects/7898789",
				"name":"Say what you see",
        "templateID": 1,
	    	"image":"http://www.lockscreen.com/projects_images/1.jpg"
			},
			"contributor":{  
        		"id":11,
        		"url":"http://api.lockscreen.com/v1/users/11",
        		"name":"Galileo Galilei",
        		"image":"http://www.lockscreen.com/profiles_images/41.jpg"
        		},
      	"createdAt":19-2-2012,
			"data":{
				"text1":"A bird",
			}
		}
	]
}
```
This endpoint retrieves the contributions in a project.

### HTTP Request

`GET http://api.lockscreen.com/v1/projects/<PROJECT_ID>/results`

<aside class="notice">
This action is paginated. See the pagination documentation for details.
</aside>
