# [Curl](https://curl.haxx.se/docs/manpage.html)

`curl -i http://localhost:8080/u/b2xVn2`
-i, --include:

vagrant [w3]> curl -i http://localhost:8080/u/b2xVn2
HTTP/1.1 302 Found
X-Powered-By: Express
Location: http://www.lighthouselabs.ca
Vary: Accept
Content-Type: text/plain; charset=utf-8
Content-Length: 50
Date: Mon, 08 Jul 2019 22:58:09 GMT
Connection: keep-alive

Found. Redirecting to http://www.lighthouselabs.ca

`curl -L http://localhost:8080/u/b2xVn2`
-L, --location:

>>> Returns the content of the new URL. (it was redirected)

