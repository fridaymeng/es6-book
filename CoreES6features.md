#### From var to const/let

```js
let x = 3
function func(randomize) {
  if (randomize) {
    let x = Math.random()
    return x
  }
  return x
}
func(false) // 3
```

- Prefer const. You can use it for all variables whose values never change.
- Otherwise, use let – for variables whose values do change.
- Avoid var.

#### From IIFEs to blocks

In ES5, you had to use a pattern called IIFE (Immediately-Invoked Function Expression) if you wanted to restrict the scope of a variable tmp to a block:

```js
(function () {  // open IIFE
    var tmp = ···;
    ···
}());  // close IIFE

console.log(tmp); // ReferenceError
```

In ECMAScript 6, you can simply use a block and a let declaration (or a const declaration):

```js
{  // open block
    let tmp = ···;
    ···
}  // close block

console.log(tmp); // ReferenceError
```

#### From concatenating strings to template literals

With ES6, JavaScript finally gets literals for string interpolation and multi-line strings.

```js
function printCoord(x, y) {
  console.log(`(${x}, ${y})`)
}
```

```js
const HTML5_SKELETON = `
    <!doctype html>
    <html>
    <head>
        <meta charset="UTF-8">
        <title></title>
    </head>
    <body>
    </body>
    </html>`
```

#### From function expressions to arrow functions

```js
function UiComponent() {
  var button = document.getElementById('myButton')
  button.addEventListener('click', () => {
    console.log('CLICK')
    this.handleClick() // (A)
  })
}
```

```js
const arr = [1, 2, 3]
const squares = arr.map(x => x * x)
```

#### Handling multiple return values

##### Multiple return values via arrays

````js
const [, year, month, day] =
    /^(\d\d\d\d)-(\d\d)-(\d\d)$/
    .exec('2999-12-31');
    ```
````

##### Multiple return values via objects

```js
const obj = { foo: 123 }
const { writable, configurable } = Object.getOwnPropertyDescriptor(obj, 'foo')
console.log(writable, configurable) // true true
```

{writable, configurable} is an abbreviation for:
{ writable: writable, configurable: configurable }

#### From for to forEach() to for-of

```js
const arr = ['a', 'b', 'c']
for (const elem of arr) {
  console.log(elem)
}
```

```js
for (const [index, elem] of arr.entries()) {
  console.log(index + '. ' + elem)
}
```

#### Handling parameter default values

```js
function foo(x=0, y=0) {
    ···
}
```

#### Handling named parameters

```js
function selectEntries({ start=0, end=-1, step=1 } = {}) {
    ···
}
```

#### From arguments to rest parameters

```js
function logAllArguments(...args) {
  for (const arg of args) {
    console.log(arg)
  }
}
function format(pattern, ...args) {
    ···
}
```

#### From apply() to the spread operator (...)

```js
Math.max(...[-1, 5, 11, 3])
```

```js
const arr1 = ['a', 'b']
const arr2 = ['c', 'd']

arr1.push(...arr2)
```

#### From concat() to the spread operator (...)

```js
const arr1 = ['a', 'b']
const arr2 = ['c']
const arr3 = ['d', 'e']

console.log([...arr1, ...arr2, ...arr3])
```

#### From function expressions in object literals to method definitions

```js
const obj = {
    foo() {
        ···
    },
    bar() {
        this.foo();
    },
}
```

#### From constructors to classes

```js
class Person {
  constructor(name) {
    this.name = name
  }
  describe() {
    return 'Person called ' + this.name
  }
}
```

```js
class Employee extends Person {
  constructor(name, title) {
    super(name)
    this.title = title
  }
  describe() {
    return super.describe() + ' (' + this.title + ')'
  }
}
```

#### From custom error constructors to subclasses of Error

```js
class MyError extends Error {}
```

#### From objects to Maps

```js
const map = new Map()
function countWords(word) {
  const count = map.get(word) || 0
  map.set(word, count + 1)
}
```

#### New string methods

```js
if (str.indexOf('x') === 0) {
} // ES5
if (str.startsWith('x')) {
} // ES6
```

```js
function endsWith(str, suffix) {
  // ES5
  var index = str.indexOf(suffix)
  return index >= 0 && index === str.length - suffix.length
}
str.endsWith(suffix) // ES6
```

```js
if (str.indexOf('x') >= 0) {
} // ES5
if (str.includes('x')) {
} // ES6
```

```js
new Array(3 + 1).join('#') // ES5
'#'.repeat(3) // ES6
```

#### New Array methods

##### From Array.prototype.indexOf to Array.prototype.findIndex

```js
const arr = ['a', NaN]
arr.indexOf(NaN) // -1
arr.findIndex(x => Number.isNaN(x)) // 1
```

```js
> isNaN('abc')
true
> Number.isNaN('abc')
false
```

##### From Array.prototype.slice() to Array.from() or the spread operator

```js
var arr1 = Array.prototype.slice.call(arguments) // ES5
const arr2 = Array.from(arguments) // ES6
```

```js
const arr1 = [...'abc']
// ['a', 'b', 'c']
const arr2 = [...new Set().add('a').add('b')]
// ['a', 'b']
```

##### From apply() to Array.prototype.fill()

```js
const arr1 = new Array(2).fill(undefined)
const arr1 = new Array(2).fill('x')
```

#### From CommonJS modules to ES6 modules

#####Multiple exports

In CommonJS, you export multiple entities as follows:

```js
//------ lib.js ------
var sqrt = Math.sqrt
function square(x) {
  return x * x
}
function diag(x, y) {
  return sqrt(square(x) + square(y))
}
module.exports = {
  sqrt: sqrt,
  square: square,
  diag: diag
}
```

```js
//------ main1.js ------
var square = require('lib').square
var diag = require('lib').diag

console.log(square(11)) // 121
console.log(diag(4, 3)) // 5
```

or

```js
//------ main2.js ------
var lib = require('lib')
console.log(lib.square(11)) // 121
console.log(lib.diag(4, 3)) // 5
```

In ES6, multiple exports are called named exports and handled like this:

```js
//------ lib.js ------
export const sqrt = Math.sqrt
export function square(x) {
  return x * x
}
export function diag(x, y) {
  return sqrt(square(x) + square(y))
}
```

```js
//------ main1.js ------
import { square, diag } from 'lib'
console.log(square(11)) // 121
console.log(diag(4, 3)) // 5
```

The syntax for importing modules as objects looks as follows (line A):

```js
//------ main2.js ------
import * as lib from 'lib' // (A)
console.log(lib.square(11)) // 121
console.log(lib.diag(4, 3)) // 5
```

##### Single exports

Single exports in CommonJS

```js
//------ myFunc.js ------
module.exports = function () { ··· };

//------ main1.js ------
var myFunc = require('myFunc');
myFunc();
```

Single exports in ES6

```js
//------ myFunc.js ------
export default function () { ··· } // no semicolon!

//------ main1.js ------
import myFunc from 'myFunc';
myFunc();
```
