# Categories

## List all categories

```http
GET /categtories HTTP/1.1
Content-Type: application/json; charset=utf-8
```

> The above command returns JSON structured like this

```http
HTTP/1.1 206 Partial Content
Content-Type: application/json
```

```json
{  
  "categories":[  
    {  
      "id":458,
      "url":"http://api.sengab.com/v1/categories/458",
      "name":"health",
      "image":"http://www.sengab.com/categories_images/458.jpg",
      "description":"This category contains all projects related to heath"
    },
    {  
      "id":584,
      "url":"http://api.sengab.com/v1/categories/584",
      "name":"science",
      "image":"http://www.sengab.com/categories_images/584.jpg",
      "description":"This category contains all projects related to science"
    }
  ],
  "next_id":-1,
  "total":2
}
```
This endpoint retrieves all categories.

### HTTP Request

`GET http://api.sengab.com/v1/categories`

<aside class="notice">
This action is paginated. See the pagination documentation for details.
</aside>

## List projects of a category

```http
GET /categtories/458 HTTP/1.1
Content-Type: application/json; charset=utf-8
```

> The above command returns JSON structured like this

```http
HTTP/1.1 206 Partial Content
Content-Type: application/json
```

```json
{  
  "id":"458",
  "url":"http://api.sengab.com/v1/categories/458",
  "name":"health",
  "image_background":"http://www.sengab.com/categories_images/458_bg.jpg",
  "projects":[  
    {  
      "id":13,
      "url":"http://api.sengab.com/v1/projects/13",
      "name":"Show me a pet",
      "image":"http://www.sengab.com/projects_images/7.jpg",
      "owner":{  
        "id":41,
        "url":"http://api.sengab.com/v1/users/41",
        "name":"Albert Einstein"
      },
      "created_at":"2008-01-14T04:33:35Z",
      "brief_description":"This a brief description about this project",
      "template_id":3,
      "is_featured":true,
      "enrollments_count":1730,
      "contributions_count":1542,
      "goal":4000,
      "progress":38.55
    }
  ],
  "next_id":-1,
  "total":1
}
```

This endpoint retrieves projects of a category.

### HTTP Request

`GET http://api.sengab.com/v1/categories/<CATEGORY_ID>`

<aside class="notice">
This action is paginated. See the pagination documentation for details.
</aside>
