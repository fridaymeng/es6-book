### Callable entities in ECMAScript 6

#### Avoid IIFEs in ES6

In ES5, you had to use an IIFE if you wanted to keep a variable local:

```js
(function () {  // open IIFE
    var tmp = ···;
    ···
}());  // close IIFE
console.log(tmp); // ReferenceError
```

In ECMAScript 6, you can simply use a block and a let or const declaration:

```js
{  // open block
    let tmp = ···;
    ···
}  // close block
console.log(tmp); // ReferenceError
```

```js
// my_module.js

// Module-private variable:
let countInvocations = 0;

export function myFunc(x) {
    countInvocations++;
    ···
}
```

```js
import { myFunc } from 'my_module.js'

myFunc(33)
```

#### Traditional functions

Function expression:

```js
  const foo = function (x) { ··· };
```

Function declaration:

```js
function foo(x) { ··· }
```

#### Generator functions

Generator function expression:

```js
  const foo = function* (x) { ··· };
```

Generator function declaration:

```js
  function* foo(x) { ··· }
```

#### Method definitions

```js
const obj = {
  add(x, y) {
    return x + y
  }, // comma is required
  sub(x, y) {
    return x - y
  } // comma is optional
}
```

```js
class AddSub {
  add(x, y) {
    return x + y
  } // no comma
  sub(x, y) {
    return x - y
  } // no comma
}
```

#### Generator method definitions

```js
const obj = {
    * generatorMethod(···) {
        ···
    },
};
class MyClass {
    * generatorMethod(···) {
        ···
    }
}
```

Arrow functions are explained in their own chapter:

```js
const squares = [1, 2, 3].map(x => x * x)
```

#### Classes

```js
// Base class: no `extends`
class Point {
  constructor(x, y) {
    this.x = x
    this.y = y
  }
  toString() {
    return `(${this.x}, ${this.y})`
  }
}
```

```js
// This class is derived from `Point`
class ColorPoint extends Point {
  constructor(x, y, color) {
    super(x, y)
    this.color = color
  }
  toString() {
    return super.toString() + ' in ' + this.color
  }
}
```
