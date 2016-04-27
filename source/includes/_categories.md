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
[
  {
    "id": "category::6",
    "url": "http://api.sengab.com/v1/categories/category::6",
    "name": "charity",
    "image": "http://www.sengab.com/categories_images/431.jpg",
    "description": "This category contains all projects related to charity"
  },
  {
    "id": "category::5",
    "url": "http://api.sengab.com/v1/categories/category::5",
    "name": "health",
    "image": "http://www.sengab.com/categories_images/458.jpg",
    "description": "This category contains all projects related to heath"
  },
  {
    "id": "category::1",
    "url": "http://api.sengab.com/v1/categories/category::1",
    "name": "health",
    "image": "http://www.sengab.com/categories_images/458.jpg",
    "description": "This category contains all projects related to heath"
  },
  {
    "id": "category::4",
    "url": "http://api.sengab.com/v1/categories/category::4",
    "name": "sports",
    "image": "http://www.sengab.com/categories_images/495.jpg",
    "description": "This category contains all projects related to sports"
  },
  {
    "id": "category::3",
    "url": "http://api.sengab.com/v1/categories/category::3",
    "name": "sports",
    "image": "http://www.sengab.com/categories_images/495.jpg",
    "description": "This category contains all projects related to sports"
  },
  {
    "id": "category::2",
    "url": "http://api.sengab.com/v1/categories/category::2",
    "name": "sports",
    "image": "http://www.sengab.com/categories_images/495.jpg",
    "description": "This category contains all projects related to sports"
  }
]
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
[
  {
    "id": "project::4",
    "name": "project 4",
    "owner": {
      "id": "user::6",
      "url": "http://api.sengab.com/v1/users/user::6",
      "name": "Ahmed Rashwan",
      "image": "http://Sengab.com/users_images/user_6.png"
    },
    "url": "http://api.sengab.com/v1/projects/project::4",
    "goal": 159,
    "image": "http://Sengab.com/projects/prject::4/image.png",
    "template_id": 1,
    "created_at": "2015-02-15T04:33:35Z",
    "brief_description": "short",
    "enrollments_count": 489,
    "contributions_count": 123,
    "category": {
      "category_id": "category::6",
      "url": "http://api.sengab.com/v1/categories/category::6",
      "name": "charity"
    }
  }
]
```

This endpoint retrieves projects of a category.

### HTTP Request

`GET http://api.sengab.com/v1/categories/<CATEGORY_ID>`

<aside class="notice">
This action is paginated. See the pagination documentation for details.
</aside>
