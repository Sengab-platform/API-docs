# Templates
Currently, we provide 6 static templates for projects, we will illustrate their structure through the following examples.

## Template 1

> Add project

```json
{
    "templateID": 1,
    "templateBody": {
        "questionTitle" : "Are you happy today?"
    }
}
```

> Submit contribution

```json
{
    "data": {
        "location" : {
          "lat": -33.8709434,
          "lng": 151.1903114
        },
        "answer" : "yes"
    }
}
```

> List results of project

```json
{
	"results": {
		"yes": [{
			"lat": -33.86755700000001,
			"lng": 151.201527
		}, {
			"lat": -33.86755700000001,
			"lng": 151.201527
		}],
		"no": [{
			"lat": -33.86755700000001,
			"lng": 151.201527
		}, {
			"lat": -33.86755700000001,
			"lng": 151.201527
		}]
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
answer       | String  | User's answer to the question                        | yes


### LIST RESULTS OF PROJECT
`result` object, holds processed location data.

Parameter | Type   | Description
----------|--------|-------------
yes       | Array  | List all location contributions with answer `yes`
no        | Array  | List all location contributions with answer `no`


## Template 2

### Description :

The result of this project will be shown as a photo grid with captions. So we will need to return the all submissions as a one result. e.g


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

> List Results for porject :

```json
{
    "results": {
        "contributions": [{
        "ID": 47878,
        "url": "http://api.lockscreen.com/v1/contributions/47878",
        "contributor": {
            "id": 11,
            "url": "http://api.lockscreen.com/v1/users/11",
            "name": "Galileo Galilei",
            "image": "http://www.lockscreen.com/profiles_images/41.jpg"
        },
        "createdAt": "2016-02-12T03:21:55Z",
        "data": {}
    }]
    }
}
```





Question Type | Question Field | Response Field | Required
------------- | ------------- | -------------- | --------
Image | imageQuestion | imageResponse | Yes
Caption  | - | captionResponse | No


List of images |
-------------- |
"http://www.lockscreen.com/submissions_images/41.jpg", "http://www.lockscreen.com/submissions_images/42.jpg" |


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

> List Results for porject :

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

> List Results for porject :

```json
{
    "data": {}
}
```


Question Type | Question Field | Response Field | Required
------------- | ------------ | -------------- | --------
Location | locationQuestion | locationResponse | Yes
Image | imageQuestion | imageResponse | Yes

The result of this project will be a combination of the responses that have a map with a marker of the user location and an image.
