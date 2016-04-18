# Templates
Currently, we provide 6 static templates for projects, we will illustrate their structure through the following examples.

## Template 1

> Add project

```json
{
  "template_id":1,
  "template_body":{
    "question_title":"Are you happy today?"
  }
}
```

> Submit contribution

```json
{  
  "data":{  
    "location":{  
      "lat":-33.8709434,
      "lng":151.1903114
    },
    "answer":"yes"
  }
}
```

> List results of project

```json
{  
  "results":{  
    "yes":[  
      {  
        "lat":-33.86755700000001,
        "lng":151.201527
      },
      {  
        "lat":-33.86755700000001,
        "lng":151.201527
      }
    ],
    "no":[  
      {  
        "lat":-33.86755700000001,
        "lng":151.201527
      },
      {  
        "lat":-33.86755700000001,
        "lng":151.201527
      }
    ]
  }
}
```

### DESCRIPTION
In this template the `Location` will not be shown to the user in the project as a question, but it will be sent implicitly alongside his response to the yes/no question.

The result of this project will be shown as a map with two types of markers indicating the answer to the question in this location. So we will need to return all location contributions as a single result.

### ADD PROJECT
Parameter                  | Type   | Description
---------------------------|------- | --------------
template_id                 | Number | Defines the template type.
template_body               | Object | Defines the template body.
template_body.question_title | String | Defines the question.


### SUBMIT CONTRIBUTION
`data` object, holds contribution data (response).

Parameter    | Type    | Description                                          | Required
-------------|---------| -----------------------------------------------------|---------
location     | Object  | Holds the value of the location (longitude/latitude).| YES
location.lat | Number  | Holds the value of latitude.                         | YES
location.lng | Number  | Holds the value of longitude.                        | YES
answer       | String  | Holds contributor's answer to the question           | YES


### LIST RESULTS OF PROJECT
`results` object, holds processed location data.

Parameter | Type   | Description
----------|--------|-------------
yes       | Array  | Lists all location contributions with answer `yes`
no        | Array  | Lists all location contributions with answer `no`


## Template 2

> Add project

```json
{  
  "template_id":2,
  "template_body":{  
    "image_title":"Take a photo of your pet."
  }
}
```

> Submit contribution

```json
{  
  "data":{  
    "image":"R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7",
    "caption":"My cat lily"
  }
}
```

> List results of project

```json
{  
  "results":[  
    {  
      "image_url":"http://www.sengab.com/projects_uploads/56842.jpg",
      "caption":"My cat lily"
    },
    {  
      "image_url":"http://www.sengab.com/projects_uploads/41242.jpg",
      "caption":"Dory, my fish"
    }
  ]
}
```

### DESCRIPTION

In this template, the project owner wants to collect images with a specific description.

The result of this project will be shown as a photo grid with the caption of each photo.

### ADD PROJECT
Parameter                  | Type   | Description
---------------------------|------- | --------------
template_id                 | Number | Defines the template type.
template_body               | Object | Defines the template body.
template_body.image_title      | String | Defines the description of required image.


### SUBMIT CONTRIBUTION
`data` object, holds contribution data (response).

Parameter    | Type   | Description                             | Required
-------------|--------|-----------------------------------------|---------
image        | String | Base64 value of the image.              | YES
caption      | String | Contributor's description of his image. | YES


### LIST RESULTS OF PROJECT
`results` array, holds images' URLs and captions.

Parameter | Type   | Description
----------|--------|-------------
image_url | String | Contribution image URL.
caption   | String | Contributor's description of his submitted image.

## Template 3

> Add Project

```json
{  
  "template_id":3,
  "template_body":{  
    "questions_count":2,
    "questions":[  
      { 
        "id":"1",
        "title":"You are a teenager ?"
      },
      {  
        "id":"2",
        "title":"Do you think you are social ?"
      }
    ]
  }
}
```

> Enroll

```json
{  
  "template_body":{  
    "questions_count":2,
    "questions":[  
      {  
        "id":1,
        "title":"You are a teenager ?"
      },
      {  
        "id":2,
        "title":"Do you think you are social ?"
      }
    ]
  }
}
```

> Submit contribution

```json
{  
  "data":{  
    "answers":[  
      {  
        "id":1,
        "ans":"yes"
      },
      {  
        "id":2,
        "ans":"no"
      }
    ]
  }
}
```

> List results for project

```json
{  
  "results":[  
    {  
      "id":1,
      "title":"You are a teenager ?",
      "contributions_count":454,
      "yes_count":45,
      "no_count":55
    },
    {  
      "id":2,
      "title":"Do you think you are social ?",
      "contributions_count":454,
      "yes_count":68,
      "no_count":32
    }
  ]
}
```

### DESCRIPTION

In this template, the project owner wants to conduct a survey about a specific topic.

The results of this project will be displayed as a chart for each question showing the percentage of yes and no answers to the question.

### ADD PROJECT
Parameter                    | Type          | Description
-----------------------------| --------------| --------------
template_id                   | Number        | Defines the template type.
template_body                 | Object        | Defines the template body.
template_body.questions_count  | Number        | Defines the number of questions in the survey (MAX = 10).
template_body.questions       | Array[Object] | Defines the questions of the survey.
template_body.questions.id    | Number        | ID of the question.
template_body.questions.title | String        | Title of the question.

### ENROLL IN A PROJECT
`template_body` object, holds the project body.

Parameter      | Type   | Description
-------------- |--------| -----------------------------------------------
questions_count | Number | The number of the questions in the survey
questions      | Object | Holds the id & title of the question
questions.id   | Number | Defines the ID of the question.
questions.title| Number | Defines the title of the question.

### SUBMIT CONTRIBUTION
`data` object, holds contribution data (response).

Parameter    | Type             | Description                                                 | Required
------------ | ---------------- | ----------------------------------------------------------- | --------
answers      | Array            | Holds IDs of questions and values of their answers(yes/no). | YES
answers.id   | Number           | ID of the question.                                         | YES
answers.ans  | String           | Answer of the question.                                     | YES


### LIST RESULTS OF PROJECT
`results` array of objects, each has the following fields.

Parameter    | Type     | Description                                  | Required
------------ | -------- | -------------------------------------------- | --------
id           | Number   | Question ID.                              | YES
title        | text     | Question Title.                        | YES
contributions_count | Number | count of contributions of question | YES
yes_percent  | Number   | holds `yes` answers percentage to question.  | YES
no_percent   | Number   | holds `no` answers percentage to question.   | YES


## Template 4

> Add Project :

```json
{
  "template_id":4,
  "template_body":{
    "image_title":"Take a photo of road accidents you witness"
  }
}
```
> Add Contribution :

```json
{
  "data":{
    "image":"R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7",
    "caption":"Accident in Tahrir Square",
    "location":{
      "lat":4545754,
      "lng":4546486
    }
  }
}
```

> List Results for project :

```json
{
  "results":[
    {
      "image_url":"http://www.sengab.com/projects_uploads/31.jpg",
      "caption":"Accident in Tahrir Square",
      "location": {
        "lat":5568,
        "lng":5775
      }
    }
  ]
}
```

###DESCRIPTION
In this template the contributor is asked to take a photo, briefly describe it and his location will be implicitly sent alongside with them.

The results will be a combination of the contributions, a map with a marker of the user location and his submitted image including the caption.

### ADD PROJECT

Parameter                  | Type         | Description
---------------------------|--------------|-------------
template_id                 | Number       | Defines the template type.
template_body               | Object       | Defines the template body.
template_body.image_title    | String       | Defines the description of required image.


### SUBMIT CONTRIBUTION
`data` object, holds contribution data (response).

Parameter    | Type    | Description                                            | Required
-------------|---------|--------------------------------------------------------|---------
image        | String  | Base64 value of the image.                             | YES
caption      | String  | Contributor's description of his image.                | YES
location     | Object  | Holds the value of the location (longitude/latitude).  | YES
location.lat | Number  | Holds the value of latitude.                           | YES
location.lng | Number  | Holds the value of longitude.                          | YES


### LIST RESULTS OF PROJECT
`results` array of objects, each has the following fields.

Parameter      | Type         | Description
---------------|--------------|----------------------------------------------------
image_url       | String       | The URL of the photo.
caption        | String       | Contributor's description of his image.
contributions_count | Number | count of all contributions for this image
location       | Object       | Holds the value of the location (longitude/latitude).
location.lat   | Number       | Holds the value of latitude.
location.lng   | Number       | Holds the value of longitude.

## Template 5

> Add project

```json
{  
  "template_id":5,
  "template_body":{  
    "question_title":"Do you see a cat?",
    "images":[  
      {  
        "image":"R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7"
      },
      {  
        "image":"R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7"
      }
    ]
  }
}
```
> Enroll

```json
{  
  "template_body":{  
    "question_title":"Do you see a cat?",
    "images":[  
      {  
        "id":1,
        "url":"http://www.sengab.com/projects_uploads/14/41.jpg"
      },
      {  
        "id":2,
        "url":"http://www.sengab.com/projects_uploads/14/42.jpg"
      },
      {  
        "id":3,
        "url":"http://www.sengab.com/projects_uploads/14/43.jpg"
      },
      {  
        "id":4,
        "url":"http://www.sengab.com/projects_uploads/14/44.jpg"
      },
      {  
        "id":5,
        "url":"http://www.sengab.com/projects_uploads/14/45.jpg"
      }
    ]
  }
}
```


> Get more feed


```http
GET /projects/15214/feed HTTP/1.1
Content-Type: application/json; charset=utf-8
```

```text
Respone :
```

```http
HTTP/1.1 206 Partial Content
Content-Type: application/json
```

```json
{  
  "images":[  
    {  
      "id":6,
      "url":"http://www.sengab.com/projects_images/14/46.jpg"
    },
    {  
      "id":7,
      "url":"http://www.sengab.com/projects_images/14/47.jpg"
    },
    {  
      "id":8,
      "url":"http://www.sengab.com/projects_images/14/48.jpg"
    },
    {  
      "id":9,
      "url":"http://www.sengab.com/projects_images/14/49.jpg"
    },
    {  
      "id":10,
      "url":"http://www.sengab.com/projects_images/14/50.jpg"
    }
  ]
}
```

> Submit contribution

```json
{
  "data": {
    "image_id": 1,
    "answer": "yes"
  }
}
```

> List results of project

```json
{  
  "results":[  
    {  
      "image_id":1,
      "image_url":"http://www.sengab.com/projects_uploads/3/1.jpg",
      "contributions_count":454,
      "yes_count":54,
      "no_count":46
    },
    {  
      "image_id":2,
      "image_url":"http://www.sengab.com/projects_uploads/3/2.jpg",
      "contributions_count":77,
      "yes_count":30,
      "no_count":70
    }
  ]
}
```

### DESCRIPTION

In this template the project has a large number of photos and we want to know if they are photos of a particular thing or not. e.g you have a 10K photos of some animals and you want to know which photos are photos of cat.

The result of this project will be each photo with the percentage of contributors' answers to the question.

### ADD PROJECT
Parameter                  | Type           | Description
---------------------------|----------------| -----------------------------------------------
template_id                 | Number         | Defines the template type.
template_body               | Object         | Defines the template body.
template_body.question_title | String         | The question that will be shown with the photos.
template_body.images        | Array[String]  | An array of string containing images in Base64.

### ENROLL IN A PROJECT
`template_body` object, holds the project body.

Parameter     | Type   | Description
--------------|--------| -----------------------------------------------
question_title | String | The question that will be shown with the photos.
image         | Object | Defines the template body.
image.id      | Number | Server-Side generated ID of the image.
image.url     | String | URL of the image.


### GET MORE FEED
This request is sent to get 5 more photos that user can contribute identifying them.

`GET http://api.sengab.com/v1/projects/<PROJECT_ID>/feed`


### SUBMIT CONTRIBUTION
`data` object, holds contribution data (response).

Parameter    | Type    | Description                                            | Required
-------------|---------| -------------------------------------------------------|---------
image_id     | Number  | The image ID of the photo that the user had recognized.| YES
answer       | Boolean | User's answer to the question                          | YES


### LIST RESULTS OF PROJECT
`results` array of objects, each has the following fields.

Parameter      | Type    | Description
---------------|---------|-------------
image_id       | Number  | The ID of the photo.
image_url      | String | URL of the image.
contributions_count | Number | count of all contributions for this image.
yes_percentage | Number  | The percentage of the positive answer that the photo had received.
no_percentage  | Number  | The percentage of the negative answer that the photo had received.


## Template 6

> Add project

```json
{
  "template_id": 6,
  "template_body": {
    "question_title": "Write what you read",
    "images": [
      {
        "image": "R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7"
      },
      {
        "image": "R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7"
      }
    ]
  }
}
```

> Enroll

```json
{  
  "template_body":{  
    "question_title":"Write what you read",
    "images":[  
      {  
        "id":1,
        "url":"http://www.sengab.com/projects_uploads/14/41.jpg"
      },
      {  
        "id":2,
        "url":"http://www.sengab.com/projects_uploads/14/42.jpg"
      },
      {  
        "id":3,
        "url":"http://www.sengab.com/projects_uploads/14/43.jpg"
      },
      {  
        "id":4,
        "url":"http://www.sengab.com/projects_uploads/14/44.jpg"
      },
      {  
        "id":5,
        "url":"http://www.sengab.com/projects_uploads/14/45.jpg"
      }
    ]
  }
}
```

> Get more feed


```http
GET /projects/15214/feed HTTP/1.1
Content-Type: application/json; charset=utf-8
```

```text
Respone :
```

```http
HTTP/1.1 206 Partial Content
Content-Type: application/json
```

```json
{  
  "images":[  
    {  
      "id":6,
      "url":"http://www.sengab.com/projects_uploads/14/46.jpg"
    },
    {  
      "id":7,
      "url":"http://www.sengab.com/projects_images/14/47.jpg"
    },
    {  
      "id":8,
      "url":"http://www.sengab.com/projects_images/14/48.jpg"
    },
    {  
      "id":9,
      "url":"http://www.sengab.com/projects_images/14/49.jpg"
    },
    {  
      "id":10,
      "url":"http://www.sengab.com/projects_images/14/50.jpg"
    }
  ]
}
```

> Submit contribution

```json
{
  "data": [
    {
      "image_id": 1,
      "text": "Sengab is just awesome!!"
    }
  ]
}
```

> List results of project

```json
{  
  "results":[  
    {  
      "image_id":1,
      "image_url":"http://www.sengab.com/projects_imags/3/1.jpg",
      "contributions_count":600,
      "text":[  
        "Sengab is just awesome!!",
        "sengab is just awesome"
      ]
    },
    {  
      "id":2,
      "image_url":"http://www.sengab.com/projects_imags/3/2.jpg",
      "contributions_count":454,
      "text":[  
        "GitHub is how people build software."
      ]
    }
  ]
}
```

### DESCRIPTION

In this template the project has a large number of scanned photos that contain text and we want to extract the text written from them. e.g you have a very old scanned book with hundreds of photos, and you want to convert it to a digital book, you will split it into a large number of photos and upload them to the project, then see the magic.

The result of this project will be every photo beside the all the text provided by the users for it.

### ADD PROJECT

Parameter                  | Type         | Description
---------------------------|------------- | ------------
template_id                 | Number       | Defines the template type.
template_body               | Object       | Defines the template body.
template_body.images        | Array        | An array of objects containing images in Base64 and their IDs.
template_body.images.image  | String       | The image represented in Base64.

### ENROLL IN A PROJECT
`template_body` object, holds the project body.

Parameter     | Type   | Description
--------------|--------| -----------------------------------------------
question_title | String | The question that will be shown with the photos.
image         | Object | Defines the template body.
image.id      | Number | Server-Side generated ID of the image.
image.url     | String | URL of the image.



### GET MORE FEED

This request is sent to get 5 more photos that user can contribute identifying them

`GET http://api.sengab.com/v1/projects/<PROJECT_ID>/feed`


### SUBMIT CONTRIBUTION
`data` object, holds contribution data (response).

Parameter    | Type    | Description                                            | Required
-------------|---------| -------------------------------------------------------|---------
image_id     | Number  | The image ID of the photo that the user had recognized.| YES
text         | String  | User's recognition to the text in the photo            | YES


### LIST RESULTS OF PROJECT
`results` array of objects, each has the following fields.

Parameter      | Type          | Description
---------------|---------------|-------------
image_id       | Number        | The ID of the photo.
image_url      | String        | URL of the image.
text           | Array[String] | A list holds all the text provided from the user for this photo.
