# [Express] (http://expressjs.com/)
DISCLAIMER: Most of these notes are directly taken from the [express website](http://expressjs.com/) and are just regrouped here for my personnal convenience.

Description:
Fast, unopinionated, minimalist web framework for Node.js.

## [Routing] (http://expressjs.com/en/guide/routing.html)
_(how an application’s endpoints (URIs) respond to client requests.)_

## [Methods] (http://expressjs.com/en/4x/api.html#app.METHOD)
### next()
hand off control to the next callback, where multiple callbacks.

### app.get()
handle GET requests

Example:
```javascript
// GET method route
app.get('/', function (req, res) {
  res.send('GET request to the homepage')
})
```

### app.post()

handle POST requests

Example:
```javascript
// POST method route
app.post('/', function (req, res) {
  res.send('POST request to the homepage')
})
```

### app.all()
handle all HTTP methods

Example:
```javascript
app.all('/secret', function (req, res, next) {
  console.log('Accessing the secret section ...')
  next() // pass control to the next handler
})
```
### app.use()
specify middleware as the callback function


## [Route paths] (http://expressjs.com/en/guide/routing.html#route-paths)

### Route Path supports Regex:
Example:
```javascript
app.get('/ab+cd', function (req, res) {
  res.send('ab+cd')
})
```
would match abcd, abbcd, abbbcd, ...
## [Route parameters](http://expressjs.com/en/guide/routing.html#route-parameters)
used to capture the values specified at their position in the URL

Example:
```javascript
app.get("/urls/:shortURL", (req, res) => {
  let templateVars = { shortURL: req.params.shortURL, longURL: urlDatabase[req.params.shortURL] };
  res.render("urls_show", templateVars);
});
```

Example _(with '-')_:
```
Route path: /flights/:from-:to
Request URL: http://localhost:3000/flights/LAX-SFO
req.params: { "from": "LAX", "to": "SFO" }
```

Example _(with '.')_:
```
Route path: /plantae/:genus.:species
Request URL: http://localhost:3000/plantae/Prunus.persica
req.params: { "genus": "Prunus", "species": "persica" }
```

Example _(with RegEx)_:
```
Route path: /user/:userId(\d+)
Request URL: http://localhost:3000/user/42
req.params: {"userId": "42"}
```

## [Route handlers](http://expressjs.com/en/guide/routing.html#route-handlers)

single callback function

Example:
```javascript
app.get('/example/a', function (req, res) {
  res.send('Hello from A!')
})
```

multiple callback functions

Example:
```javascript
app.get('/example/b', function (req, res, next) {
  console.log('the response will be sent by the next function ...')
  next()
}, function (req, res) {
  res.send('Hello from B!')
})
```

array of callback functions

Example:
```javascript
var cb0 = function (req, res, next) {
  console.log('CB0')
  next()
}

var cb1 = function (req, res, next) {
  console.log('CB1')
  next()
}

var cb2 = function (req, res) {
  res.send('Hello from C!')
}

app.get('/example/c', [cb0, cb1, cb2])

```

combination of independent functions and arrays of functions

Example:
```javascript
var cb0 = function (req, res, next) {
  console.log('CB0')
  next()
}

var cb1 = function (req, res, next) {
  console.log('CB1')
  next()
}

app.get('/example/d', [cb0, cb1], function (req, res, next) {
  console.log('the response will be sent by the next function ...')
  next()
}, function (req, res) {
  res.send('Hello from D!')
})
```

## [Response methods](http://expressjs.com/en/guide/routing.html#response-methods)

* res.download() - Prompt a file to be downloaded.
* res.end() - End the response process.
* res.json() - Send a JSON response.
* res.jsonp() - Send a JSON response with JSONP support.
* res.redirect() - Redirect a request.
* res.render() - Render a view template.
* res.send() - Send a response of various types.
* res.sendFile() - Send a file as an octet stream.
* res.sendStatus() - Set the response status code and send its string representation as the response body.

## [app.route()](http://expressjs.com/en/guide/routing.html#app-route)

chainable route handlers for a route path

Example:
```javascript
app.route('/book')
  .get(function (req, res) {
    res.send('Get a random book')
  })
  .post(function (req, res) {
    res.send('Add a book')
  })
  .put(function (req, res) {
    res.send('Update the book')
  })
```

## [express.Router](http://expressjs.com/en/guide/routing.html#express-router)

mountable route handlers (mini-app) (complete middleware and routing system)
```javascript
var express = require('express')
var router = express.Router()

// middleware that is specific to this router
router.use(function timeLog (req, res, next) {
  console.log('Time: ', Date.now())
  next()
})
// define the home page route
router.get('/', function (req, res) {
  res.send('Birds home page')
})
// define the about route
router.get('/about', function (req, res) {
  res.send('About birds')
})

module.exports = router
```

router module:
```javascript
var birds = require('./birds')

// ...

app.use('/birds', birds)

```