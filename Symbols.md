### Symbols

Symbols are a new primitive type in ECMAScript 6. They are created via a factory function:

```JS
const mySymbol = Symbol('mySymbol');
```

#### unique property keys

```js
var yieldIterator = {}
yieldIterator[Symbol.iterator] = function*() {
  yield 1
  yield 2
  yield 3
}
[...yieldIterator] // [1, 2, 3]
```

```js
const iterable = {
  [Symbol.iterator]() {
    let step = 0
    const iterator = {
      next() {
        if (step <= 2) {
          step++
        }
        switch (step) {
          case 1:
            return { value: 'hello', done: false }
          case 2:
            return { value: 'world', done: false }
          default:
            return { value: undefined, done: true }
        }
      }
    }
    return iterator
  }
}
```

Let’s check that iterable is, in fact, iterable:

```js
for (const x of iterable) {
  console.log(x)
}
// Output:
// hello
// world
```

#### constants representing concepts

```js
const COLOR_RED = Symbol('Red')
const COLOR_ORANGE = Symbol('Orange')
const COLOR_YELLOW = Symbol('Yellow')
const COLOR_GREEN = Symbol('Green')
const COLOR_BLUE = Symbol('Blue')
const COLOR_VIOLET = Symbol('Violet')

function getComplement(color) {
  switch (color) {
    case COLOR_RED:
      return COLOR_GREEN
    case COLOR_ORANGE:
      return COLOR_BLUE
    case COLOR_YELLOW:
      return COLOR_VIOLET
    case COLOR_GREEN:
      return COLOR_RED
    case COLOR_BLUE:
      return COLOR_ORANGE
    case COLOR_VIOLET:
      return COLOR_YELLOW
    default:
      throw new Exception('Unknown color: ' + color)
  }
}
```

#### Symbols as property keys

```js
const MY_KEY = Symbol()
const obj = {}

obj[MY_KEY] = 123
console.log(obj[MY_KEY]) // 123
```
