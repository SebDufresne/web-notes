# [EJS](https://ejs.co/)

[npm link](https://www.npmjs.com/package/ejs)

Templating engine to generate HTML markup with JavaScript.


Also referred to as: view engine

We need to add the view engine call:
```javascript
app.set("view engine", "ejs");
```

`<%= %>`
Display code on our page

Example:
```javascript
<h1><%= greeting %></h1>
```

Example _(adding a header)_:
```javascript
<% include ./partials/_header %>
```

`<% %>`
Run some code, without displaying it
Example:
```javascript
<!-- This line will not show up on the page -->
<% if(greeting) {%>
  <!-- This line will only show if greeting is truthy -->
  <h1><%= greeting %></h1>
<% }%>
```


We need to send variables as objects:
```javascript
app.get("/hello", (req, res) => {
  let templateVars = { greeting: 'Hello World!' };
  res.render("hello_world", templateVars);
});
```