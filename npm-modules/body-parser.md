# body-parser

[npm reference](https://www.npmjs.com/package/body-parser)

Usage:
Converts the request body from a Buffer into string that we can read.

const bodyParser = require("body-parser");
app.use(bodyParser.urlencoded({extended: true}));
