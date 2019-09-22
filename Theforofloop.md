### The for-of loop
#### Overview
for-of is a new loop in ES6 that replaces both for-in and forEach() and supports the new iteration protocol.
```js
const iterable = ['a', 'b'];
for (const x of iterable) {
    console.log(x);
}

// Output:
// a
// b
```

break and continue work inside for-of loops:
```js
for (const x of ['a', '', 'b']) {
    if (x.length === 0) break;// or continue
    console.log(x);
}

// Output:
// a
```

Access both elements and their indices while looping over an Array (the square brackets before of mean that we are using destructuring):
```js
const arr = ['a', 'b'];
for (const [index, element] of arr.entries()) {
    console.log(`${index}. ${element}`);
}

// Output:
// 0. a
// 1. b
```

Looping over the [key, value] entries in a Map (the square brackets before of mean that we are using destructuring):
```js
const map = new Map([
    [false, 'no'],
    [true, 'yes'],
]);
for (const [key, value] of map) {
    console.log(`${key} => ${value}`);
}

// Output:
// false => no
// true => yes
```
