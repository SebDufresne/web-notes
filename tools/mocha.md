# [Mocha](https://mochajs.org) & [Chai](https://www.chaijs.com)



## Mocha
Mocha gives us the describe and it functions. Each it is a test, and each test should have at least one assertion.

## Chai
Chai is an assertion library. It gives us assertion functions so that we no longer have to use our assertEqual and other assertion functions that we implemented previously. Chai assertion functions are deliberately designed to play nice with testing frameworks like Mocha.

## Useful options

Display times for execution (higher than 1ms)

`> mocha -s 0` // Give an estimate of the time needed to run

`npx mocha`

`mocha`
`npm test`
`npm test test/test_palindromes.js`


## Environment variables

$PATH (pour package.json)
./node_modules/mocha/bin/mocha

Invocation Variations
```javascript
const chai = require('chai');
const assert = chai.assert;

const { assert } = require('chai');

const assert = require('chai').assert;
```

### [Asserts] (https://www.chaijs.com/api/assert/)

  assert.deepEqual(tail(['Hello', 'Lighthouse', 'Labs']),['Lighthouse', 'Labs']);
  assert.equal(nameInverter(inputName), expectedOutput);
  assert.exists(err);
  assert.isFalse(isPalindrome(phrase));
  assert.isTrue(isPalindrome(phrase));
  assert.strictEqual(head(['Hello', 'Lighthouse', 'Labs']), 'Hello');
  assert.throws(() => nameInverter(inputName), Error, 'Error');

strictEqual : For strict equality
deepEqual : for comparing objects and arrays

### Example

```Javascript
const assert = require('chai').assert;
const nameInverter = require('../nameInverter');

describe('nameInverter', function() {
  it("returns 'Hello' for ['Hello', 'Lighthouse', 'Labs']", () => {
    assert.strictEqual(head(['Hello', 'Lighthouse', 'Labs']), 'Hello');
  });
});
```

## [BDD Styles](https://www.chaijs.com/api/bdd/)

expect({a: 1}).to.deep.equal({a: 1});
expect({a: 1}).to.not.equal({a: 1});