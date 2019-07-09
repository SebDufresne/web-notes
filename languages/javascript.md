# JavaScript


## Primitives
six types of primitives (data type):
* undefined
* null
* boolean
* string
* number
* symbol

functions are technically a sub-category of objects

The six primitive types, plus object, make up the seven fundamental types of JavaScript.

object literal  : {}

## Truthy / Falsy
Falsy:
```javascript
False
0
''
null
undefined
NaN
```

### Destructuring (New to ES6)
[example 1](https://alligator.io/js/object-property-shorthand-es6/)
```javascript
let cat = 'Miaow';
let dog = 'Woof';
let bird = 'Peet peet';

let someObject = {
  cat,
  dog,
  bird
}

console.log(someObject);

//{
//  cat: "Miaow",
//  dog: "Woof",
//  bird: "Peet peet"
//}
```


Example 2:
```javascript
const body = {
  latitude : 3,
  longitude : 4,
};
```
This:
```javascript
const { latitude, longitude } = body;
```

Is the equivalent of this:
```javascript
const latitude = body.latitude;
const longitude = body.longitude;
```

## Functions

# [First Class function](https://en.wikipedia.org/wiki/First-class_function)

A First Class function can:
* stored in a variable, object, or array
*
*

JavaScript is single threaded -> Only one call Stack (only runs one thing at a time)

## Objects

[Object.prototype.hasOwnProperty()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/hasOwnProperty)


returns a boolean indicating whether the object has the specified property as its own property

```javascript
console.log(object1.hasOwnProperty('property1'));
```


## Promises
Promises execute in the "Main Thread"

### Four states of a promise
Fulfilled (Resolved): It worked :-)
Rejected: It didn't work :-(
Pending: Still waiting...
Settled: Something happened (Fulfilled or Rejected)