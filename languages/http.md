# HTTP

## Status Code

## [values for the first digit](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes)
* 1xx (Informational): The request was received, continuing process
* 2xx (Successful): The request was successfully received, understood and accepted
* 3xx (Redirection): Further action needs to be taken in order to complete the request
* 4xx (Client Error): The request contains bad syntax or cannot be fulfilled
* 5xx (Server Error): The server failed to fulfill an apparently valid request

### [Information responses](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#Information_responses)
100 Continue
101 Switching Protocol
102 Processing (WebDAV)
103 Early Hints

### [Successful responses](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#Successful_responses)
200 OK
201 Created
202 Accepted
203 Non-Authoritative Information
204 No Content
205 Reset Content
206 Partial Content
207 Multi-Status (WebDAV)
208 Multi-Status (WebDAV)
226 IM Used (HTTP Delta encoding)

### [Redirection messages](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#Redirection_messages)
300 Multiple Choice
301 Moved Permanently
302 Found
303 See Other
304 Not Modified
305 Use Proxy
306 unused
307 Temporary Redirect
308 Permanent Redirect

### [Client error responses](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#Client_error_responses)
400 Bad Request
401 Unauthorized
402 Payment Required
403 Forbidden
404 Not Found
405 Method Not Allowed
406 Not Acceptable
407 Proxy Authentication Required
408 Request Timeout
409 Conflict
410 Gone
411 Length Required
412 Precondition Failed
413 Payload Too Large
414 URI Too Long
415 Unsupported Media Type
416 Requested Range Not Satisfiable
417 Expectation Failed
418 I'm a teapot
421 Misdirected Request
422 Unprocessable Entity (WebDAV)
423 Locked (WebDAV)
424 Failed Dependency (WebDAV)
425 Too Early
426 Upgrade Required
428 Precondition Required
429 Too Many Requests
431 Request Header Fields Too Large
451 Unavailable For Legal Reasons

### [Server error responses](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#Server_error_responses)
500 Internal Server Error
501 Not Implemented
502 Bad Gateway
503 Service Unavailable
504 Gateway Timeout
505 HTTP Version Not Supported
506 Variant Also Negotiates
507 Insufficient Storage
508 Loop Detected (WebDAV)
510 Not Extended
511 Network Authentication Required

## [HTTP request methods] (https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)

* GET - requests a representation of the specified resource. Requests using GET should only retrieve data.
* HEAD - asks for a response identical to that of a GET request, but without the response body.
* POST - submit an entity to the specified resource, often causing a change in state or side effects on the server.
* PUT - replaces all current representations of the target resource with the request payload.
* DELETE - deletes the specified resource.
* CONNECT - establishes a tunnel to the server identified by the target resource.
* OPTIONS - describe the communication options for the target resource.
* TRACE - performs a message loop-back test along the path to the target resource.
* PATCH - apply partial modifications to a resource.

GET to read some information (safe as in a request that should have no side effects on the server).
GET request does not have a body.

## [POST](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST)
Used:
 * to create a resource.
 * to update a resource in a non-idempotent way.

POST has a body of the type spectified in [Content-Type](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Type).

PUT to update a resource in an [idempotent](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol#Idempotent_methods_and_web_applications) way.
DELETE to delete a resource.

HTTP to CRUD:
POST <---> Create
GET <---> Read
PUT <---> Update
DELETE <---> Delete

## [Safe Methods] (https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol#Safe_methods)

HEAD, OPTIONS and TRACE - only for information retrieval / node side effects

GET - planned for information retrieval, but not technically limited

POST, PUT, DELETE and PATCH - have side effects

## [Idempotent Methods] (https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol#Idempotent_methods_and_web_applications)

PUT / DELETE are idempotent, multiple identical requests should have the same effect as a single request

GET, HEAD, OPTIONS and TRACE should be idempotent since HTTP is a stateless protocol.

POST method is not necessarily idempotent, sending the request multiple times may further affect state or cause further side effects.

CONNECT / PATCH are not idempotent.