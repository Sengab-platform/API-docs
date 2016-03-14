# Templates
At this moment, we provide 6 static templates for projects, in this doc we will illustrate them and their structure while the process of add project and view the results.

## Template 1

Question Type | Question Field | Response Field | Required
------------- | ------------- | -------------- | --------
Yes/No | polarQuestion | polarResponse | Yes
Location | - | locationResponse | Yes

In this template the `Location` will not be shown to the user in the project as a question, but it will be sent along side his response to the yes/no question implicitly.

The result of this project will be shown as a map with to types of markers indication the response of the question in this location. So we will need to return the all submissions as a one result. e.g

Response | List of locations
---------| ----------
Yes | ["31.205205,31.624552", "31.047634, 31.376812"]
No | ["51.5154907,-0.1922661,12"]

## Template 2

Question Type | Question Field | Response Field | Required
------------- | ------------- | -------------- | --------
Image | imageQuestion | imageResponse | Yes
Caption  | - | captionResponse | No

The result of this project will be shown as a photo grid with captions. So we will need to return the all submissions as a one result. e.g

List of images |
-------------- |
"http://www.lockscreen.com/submissions_images/41.jpg", "http://www.lockscreen.com/submissions_images/42.jpg" |


## Template 3

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

Question Type | Question Field | Response Field | Required
------------- | ------------ | -------------- | --------
Location | locationQuestion | locationResponse | Yes
Image | imageQuestion | imageResponse | Yes

The result of this project will be a combination of the responses that have a map with a marker of the user location and an image.


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
        "answer" : true
    }
}
```

> List results of project

```json
{
	"result": {
		"images": [{
			"id": 32,
			"percentage": 65
		}, {
			"id": 2,
			"percentage": 5
		}, {
			"id": 3,
			"percentage": 0
		}]
	}
}
```

### DESCRIPTION

In this template the project has a large number of photos and we want to know if they are photos of a particular thing or not. e.g you have a 10K photos of some animals and you want to know which photos are photos of cat.

The result of this project will be every photo beside the the percentage of the people says it the thing you want.

### ADD PROJECT

Parameter                  | Type   | Description
----------------------------|------- | --------------
templateID                 | Number | Defines the template type.
templateBody               | Object | Defines the template body.
templateBody.questionTitle | String | The question that will be shown with the photos, must be a y/n question.
templateBody.images        | String | A list of the base64 of the images.


### SUBMIT CONTRIBUTION
`data` object, holds contribution data (response).

Parameter    | Type    | Description                                        | Required
-------------|---------| ---------------------------------------------------|---------
imageID      | Number  | The image ID of the photo that the user had recognized.| yes
answer       | Boolean  | User's answer to the question                         | yes


### LIST RESULTS OF PROJECT
`result` object, holds processed location data.

Parameter | Type   | Description
----------|--------|-------------
images    | Array | Holds all the images IDs and their percentage of confirmation.
images.imageID    | Number  | The ID of the photo.
images.percentage | Number  | The percentage of the positive answer that the photo had received.
