# Node JS

Integrated Server in JS

Run JS on the backend (V8 engine)

It's a JS runtime environment

Chome V8 Engine + Modules Systems npm() + i/o livraries (C++, FS, HTTP, NET)

## Server

```javascript
server.on('connection', connection => {
  ...
});
```

'connection' => name of the envent we're waiting for
connection => parameter name we can refer to for our anonymous function