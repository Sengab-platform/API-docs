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
"http://www.lockscreen.com/submissions_images/41.jpg", "http://www.lockscreen.com/submissions_images/42.jpg"


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
