git init

npm init

npm install --save-dev mocha
-g global
--save-dev : Required for develoment
--save : Required

npm install mocha chai --save-dev

npm run question 0


// Git Ignore example:
# project dependencies
node_modules

# OSX folder attributes
.DS_Store

# temporary files
*.tmp
*~
*.log


// chmod 244 package.json
-rw-r--r-- 1 vagrant vagrant   329 Jun 29 03:02 package.json


./node_modules/mocha/bin/mocha


//

{
  "name": "project-name",
  "version": "1.0.0",
  "description": "Short project summary",
  "main": "index.js",
  "scripts": {
    "myscript": "ENV=development node index.js",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "",
  "license": "MIT",
  "dependencies": {
    "express": "^4.13.4"
  }
}


npm run myscript
