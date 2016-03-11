# - Categories

## List all categories

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
  "categories":[  
    {  
      "id":458,
      "url":"http://api.lockscreen.com/v1/categories/458",
      "name":"health",
      "image":"http://www.lockscreen.com/categories_images/458.jpg",
      "description":"This category contains all projects related to heath"
    },
    {  
      "id":584,
      "url":"http://api.lockscreen.com/v1/categories/584",
      "name":"science",
      "image":"http://www.lockscreen.com/categories_images/584.jpg",
      "description":"This category contains all projects related to science"
    }
  ],
  "nextId":-1,
  "total":2
}
```
This endpoint retrieves all categories.

### HTTP Request

`GET http://api.lockscreen.com/v1/categories`

<aside class="notice">
This action is paginated. See the pagination documentation for details.
</aside>

## List projects of a category

```http
GET /categtories/458 HTTP/1.1
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
  "id":"458",
  "url":"http://api.lockscreen.com/v1/categories/458",
  "name":"health",
  "imageBackground":"http://www.lockscreen.com/category_images/458_bg.jpg",
  "projects":[  
    {  
      "id":13,
      "url":"http://api.lockscreen.com/v1/projects/13",
      "name":"Show me a pet",
      "image":"http://www.lockscreen.com/projects_images/7.jpg",
      "owner":{  
        "id":41,
        "url":"http://api.lockscreen.com/v1/users/41",
        "name":"Albert Einstein"
      },
      "createdAt":"2008-01-14T04:33:35Z",
      "briefDescription":"This a brief description about this project",
      "templateID": 3,
      "isFeatured":true,
      "enrollmentsCount":1730,
      "contributionsCount":1542,
      "goal":4000,
      "progress":38.55
    }
  ],
  "nextId":-1,
  "total":1
}
```

This endpoint retrieves projects of a category.

### HTTP Request

`GET http://api.lockscreen.com/v1/categories/<CATEGORY_ID>`

<aside class="notice">
This action is paginated. See the pagination documentation for details.
</aside>
