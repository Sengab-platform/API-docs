# Structure

## Request 1


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
    "avatar": "www.lookscreen.com/profiles_images/1411414.jpg"
}
```


This endpoint retrieves user's profile.

### HTTP Request

`GET http://api.lockscreen.com/v1/users/<ID>/`

### URL Parameters

Parameter | Description
--------- | -----------
ID |ID of the user