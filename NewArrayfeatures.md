### New Array features
#### New static Array methods

Array.from(arrayLike, mapFunc?, thisArg?)
```js
const arrayLike = { length: 2, 0: 'a', 1: 'b' };

// for-of only works with iterable values
for (const x of arrayLike) { // TypeError
    console.log(x);
}

const arr = Array.from(arrayLike);
for (const x of arr) { // OK, iterable
    console.log(x);
}
// Output:
// a
// b
```

Array.from() is also a convenient alternative to using map() generically:
```js
const spans = document.querySelectorAll('span.name');

// map(), generically:
const names1 = Array.prototype.map.call(spans, s => s.textContent);

// Array.from():
const names2 = Array.from(spans, s => s.textContent);
```
Iterating over Arrays
```js
Array.from(['a', 'b'].keys())
//  0, 1 ]
Array.from(['a', 'b'].values())
// [ 'a', 'b' ]
Array.from(['a', 'b'].entries())
// [ [ 0, 'a' ],  [ 1, 'b' ] ]
```

Searching for Array elements
```js
[6, -5, 8].find(x => x < 0)
// -5
[6, 5, 8].find(x => x < 0)
// undefined

[6, -5, 8].findIndex(x => x < 0)
// 1
[6, 5, 8].findIndex(x => x < 0)
// -1
```

Array.prototype.fill()
```js
const arr = ['a', 'b', 'c'];
arr.fill(7)
// [ 7, 7, 7 ]
arr
// [ 7, 7, 7 ]

['a', 'b', 'c'].fill(7, 1, 2)
// [ 'a', 7, 'c' ]
```
