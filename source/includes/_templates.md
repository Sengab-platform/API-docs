# Templates
At this moment, we provide 6 static templates for projects, in this doc we will illustrate them and their structure while the process of add project and view the results.

## Template 1


> Add Project :

```json
{
    "templateID": 1,
    "templateBody": {
        "questionTitle" : "Are you happy today?"
    }
}
```


> Add Contribution : 

```json
{
    "data": {
        "location" : ["31.205205,31.624552", "31.047634, 31.376812"],
        "answer" : true
    }
}
```


> List Results for porject :

```json
{
    "results": {
        "yes":[["31.205205","31.205205"],["31.205205","31.205205"]] ,
        "no": [["31.205205","31.205205"],["31.205205","31.205205"]] 
       }
}
```



### Description :

In this template the `Location` will not be shown to the user in the project as a question, but it will be sent along side his response to the yes/no question implicitly.

The result of this project will be shown as a map with to types of markers indication the response of the question in this location. So we will need to return the all submissions as a one result. e.g

### Add project :

Parameter | Type | Desc 
------------- | ------------- | -------------- 
templateID | Number | defines the template type 
templatedBody | obj | defines the template body 
templatedBody.questionTitle | String | defines the question which will appear to this project enrolled users 


### Add Contribution :

Parameter | Type | Desc | Required
------------- | ------------- | -------------- | --------
data | obj | contains the contribution data | yes
data.location | Array | contains x and y coordinates | yes
data.answer | Boolean | the User's answer for the question | yes



### List Results for project :


Parameter | Type | Desc 
--------- | ---- | -----
results | obj | contains the contribution data 
results.yes | Array | List of all x and y coordinates for contributors answered with Yes 
results.no | Array | List of all x and y coordinates for contributors answered with No




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
