# [Mocha](https://mochajs.org) & [Chai](https://www.chaijs.com)


## Mocha
Mocha gives us the describe and it functions. Each it is a test, and each test should have at least one assertion.

## Chai
Chai is an assertion library. It gives us assertion functions so that we no longer have to use our assertEqual and other assertion functions that we implemented previously. Chai assertion functions are deliberately designed to play nice with testing frameworks like Mocha.

## Useful options

Display times for execution (higher than 1ms)

`> mocha -s 0`


## [Some Syntaxes](https://www.chaijs.com/api/bdd/)

expect({a: 1}).to.deep.equal({a: 1});
expect({a: 1}).to.not.equal({a: 1});


assertStrictEqual simply uses === to compare value
assertDeepEqual for comparing objects and arrays


  it("returns 'Hello' for ['Hello', 'Lighthouse', 'Labs']", () => {
    assert.strictEqual(head(['Hello', 'Lighthouse', 'Labs']), 'Hello');
  });

  it("returns ['Lighthouse', 'Labs'] for ['Hello', 'Lighthouse', 'Labs']", () => {
    assert.deepEqual(tail(['Hello', 'Lighthouse', 'Labs']),['Lighthouse', 'Labs']);
  });