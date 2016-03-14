# Templates
Currently, we provide 6 static templates for projects, we will illustrate their structure through the following examples.

## Template 1

> Add project

```json
{
  "templateID": 1,
  "templateBody": {
    "questionTitle": "Are you happy today?"
  }
}
```

> Submit contribution

```json
{
  "data": {
    "location": {
      "lat": -33.8709434,
      "lng": 151.1903114
    },
    "answer": "yes"
  }
}
```

> List results of project

```json
{
  "results": {
    "yes": [
      {
        "lat": -33.86755700000001,
        "lng": 151.201527
      },
      {
        "lat": -33.86755700000001,
        "lng": 151.201527
      }
    ],
    "no": [
      {
        "lat": -33.86755700000001,
        "lng": 151.201527
      },
      {
        "lat": -33.86755700000001,
        "lng": 151.201527
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
templateID                 | Number | Defines the template type.
templateBody               | Object | Defines the template body.
templateBody.questionTitle | String | Defines the question.


### SUBMIT CONTRIBUTION
`data` object, holds contribution data (response).

Parameter    | Type    | Description                                          | Required
-------------|---------| -----------------------------------------------------|---------
location     | Object  | Holds the value of the location (longitude/latitude).| yes
location.lat | Number  | Holds the value of latitude.                         | yes
location.lng | Number  | Holds the value of longitude.                        | yes
answer       | String  | Holds contributor's answer to the question           | yes


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
  "templateID": 2,
  "templateBody": {
    "imageTitle": "Take a photo of your pet."
  }
}
```

> Submit contribution

```json
{
  "data": {
    "imgString": "R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7",
    "caption": "My cat lily"
  }
}
```

> List results of project

```json
{
  "results": [
    {
      "imgUrl": "http://www.sengab.com/uploads/56842.jpg",
      "caption": "My cat lily"
    },
    {
      "imgUrl": "http://www.sengab.com/uploads/41242.jpg",
      "caption": "Dory, my fish"
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
templateID                 | Number | Defines the template type.
templateBody               | Object | Defines the template body.
templateBody.imgTitle      | String | Defines the description of required image.


### SUBMIT CONTRIBUTION
`data` object, holds contribution data (response).

Parameter    | Type             | Description                                   | Required
-------------|------------------|-----------------------------------------------|---------
imgString    | String (Base64)  | Base64 value of the image.                    | yes
caption      | String           | Contributor's description of his image.       | yes


### LIST RESULTS OF PROJECT
`results` array, holds images' urls and captions.

Parameter | Type   | Description
----------|--------|-------------
imgUrl    | String | Contribution image url.
caption   | String | Contributor's description of his submitted image.

## Template 3


### Description :



> Add Project :

```json
{
    "templateID": 1,
    "templateBody": {}
}
```

> Add Contribution :

```json
{
    "data": {}
}
```

> List Results for project :

```json
{
    "data": {}
}
```


Question Type | Question Field | Response Field | Required
------------- | ------------- | -------------- | --------
Yes/No | polarQuestion1 | polarResponse1 | Yes
Yes/No | polarQuestion2 | polarResponse2 | Yes

In this template there is undefined number of yes/no questions.

The result of this project will be a chart for every question showing the percentage of yes/no responses for every question.

Question # | Yes Percentage
---------- | --------------
1 | "42.5"
2 | "73.1"

## Template 4

> Add Project :

```json
{
  "templateID": 4,
  "templateBody": {
    "imageTitle": "Take a photo of road accidents you witness"
  }
}
```
> Add Contribution :

```json
{
  "data": {
    "image": "R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7",
    "caption": "Accident in Tahrir Square",
    "location": {
      "lat": 4545754,
      "lng": 4546486
    }
  }
}
```

> List Results for project :

```json
{
  "results": [
    {
      "imageUrl": "http://www.sengab.com/projects_submissions/31.jpg",
      "caption": "Accident in Tahrir Square",
      "location": {
        "lat": 5568,
        "lng": 5775
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
templateID                 | Number       | Defines the template type.
templateBody               | Object       | Defines the template body.
templateBody.imageTitle    | String       | Defines the description of required image.


### SUBMIT CONTRIBUTION
`data` object, holds contribution data (response).

Parameter    | Type    | Description                                            | Required
-------------|---------|--------------------------------------------------------|---------
image        | String  | Base64 value of the image.                             | Yes
caption      | String  | Contributor's description of his image.                | Yes
location     | Object  | Holds the value of the location (longitude/latitude).  | Yes
location.lat | Number  | Holds the value of latitude.                           | Yes
location.lng | Number  | Holds the value of longitude.                          | Yes


### LIST RESULTS OF PROJECT
`result` array, holds processed location data.

Parameter      | Type         | Description
---------------|--------------|----------------------------------------------------
imageUrl       | String       | The URL of the photo.
caption        | String       | Contributor's description of his image.
location       | Object       | Holds the value of the location (longitude/latitude).
location.lat   | Number       | Holds the value of latitude.
location.lng   | Number       | Holds the value of longitude.

## Template 5

> Add project

```json
{
  "templateID": 5,
  "templateBody": {
    "questionTitle": "Do you see a cat?",
    "images": [
      {
        "id": 1,
        "image": "R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7"
      },
      {
        "id": 2,
        "image": "R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7"
      }
    ]
  }
}
```

> Submit contribution

```json
{
  "data": {
    "imageID": 1,
    "answer": true
  }
}
```

> List results of project

```json
{
  "results": [
    {
      "id": 1,
      "percentage": 54
    },
    {
      "id": 2,
      "percentage": 12
    }
  ]
}
```

### DESCRIPTION

In this template the project has a large number of photos and we want to know if they are photos of a particular thing or not. e.g you have a 10K photos of some animals and you want to know which photos are photos of cat.

The result of this project will be every photo beside the the percentage of the people says it the thing you want.

### ADD PROJECT

Parameter                  | Type   | Description
---------------------------|-------| --------------
templateID                 | Number | Defines the template type.
templateBody               | Object | Defines the template body.
templateBody.questionTitle | String | The question that will be shown with the photos, must be a y/n question.
templateBody.images        | Array  | An array of objects containing images in Base64 and their IDs.
templateBody.images.id     | Number | ID of the image.
templateBody.images.image  | String | The image represented in Base64.


### SUBMIT CONTRIBUTION
`data` object, holds contribution data (response).

Parameter    | Type    | Description                                            | Required
-------------|---------| -------------------------------------------------------|---------
imageID      | Number  | The image ID of the photo that the user had recognized.| yes
answer       | Boolean | User's answer to the question                          | yes


### LIST RESULTS OF PROJECT
`result` array, holds processed location data.

Parameter | Type   | Description
----------|--------|-------------
imageID    | Number  | The ID of the photo.
percentage | Number  | The percentage of the positive answer that the photo had received.

## Template 6

> Add project

```json
{
  "templateID": 6,
  "templateBody": {
    "images": [
      {
        "id": 1,
        "image": "R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7"
      },
      {
        "id": 2,
        "image": "R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7"
      }
    ]
  }
}
```

> Submit contribution

```json
{
  "data": [
    {
      "imageID": 1,
      "text": "Sengab is just awesome!!"
    }
  ]
}
```

> List results of project

```json
{
  "results": [
    {
      "id": 1,
      "text": [
        "Sengab is just awesome!!",
        "sengab is just awesome"
      ]
    },
    {
      "id": 2,
      "text": [
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
templateID                 | Number       | Defines the template type.
templateBody               | Object       | Defines the template body.
templateBody.images        | Array        | An array of objects containing images in Base64 and their IDs.
templateBody.images.id     | Number       | ID of the image.
templateBody.images.image  | String       | The image represented in Base64.


### SUBMIT CONTRIBUTION
`data` object, holds contribution data (response).

Parameter    | Type    | Description                                            | Required
-------------|---------| -------------------------------------------------------|---------
imageID      | Number  | The image ID of the photo that the user had recognized.| yes
text         | String  | User's recognition to the text in the photo            | yes


### LIST RESULTS OF PROJECT
`result` array, holds processed location data.

Parameter      | Type         | Description
---------------|--------------|-------------
imageID        | Number       | The ID of the photo.
text           | Array[String] | A list holds all the text provided from the user for this photo.