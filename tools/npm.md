# npm

## Cheat Sheet:
npm init -y

npm i mocha chai --save-dev

npm install --save-dev mocha && npm install --save-dev chai

Possible flags:
-g global
--save-dev : Required for develoment
--save : (no longer needed (on by default))

npm run myscript

## Publishing to npm:

[submitting project](https://docs.npmjs.com/creating-and-publishing-scoped-public-packages#publishing-scoped-public-packages)

Submitted project:
https://www.npmjs.com/package/@sebdufresne/lotide


Publish updates to npm:

Change the version number from "1.0.0" to "1.0.1" in package.json

Use the npm publish command again to publish the new version.