# Errors

Our API responses indicating an error or warning are represented by a proper response HTTP status code (403, 404, etc) alongside with a response body containing the following information:

Attribute	| Type | Description
--------- | ---- | ------------
status |	Number | The corresponding HTTP status code.
code |	Number | A specific error code that can be used to obtain more information.
message	| String | A simple, easy to understand message that you can show directly to your application’s end-user.

Our API uses the following error codes:

Error Code | Meaning | Details
---------- | ------- | -----
400 | Bad Request | Your request sucks !
401 | Unauthorized | Authentication credentials are required to access the resource. All requests must be authenticated.
403 | Forbidden | The supplied authentication credentials are not sufficient to access the resource.
404 | Not Found |  We could not locate the resource based on the specified URL.
405 | Method Not Allowed | This request is not supported for the resource.
406 | Not Acceptable | You requested a format that isn't JSON.
409 | Conflict | The request could not be completed due to a conflict with the current state of the target resource.
500 | Internal Server Error | We had a problem with our server. Try again later.
503 | Service Unavailable | We're temporarily offline for maintenance, Please try again later.
