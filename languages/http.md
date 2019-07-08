# HTTP

## Status Code

## [values for the first digit](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes)
* 1xx (Informational): The request was received, continuing process
* 2xx (Successful): The request was successfully received, understood and accepted
* 3xx (Redirection): Further action needs to be taken in order to complete the request
* 4xx (Client Error): The request contains bad syntax or cannot be fulfilled
* 5xx (Server Error): The server failed to fulfill an apparently valid request

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

POST to create a resource.
POST to update a resource in a non-idempotent way.
POST has a body

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