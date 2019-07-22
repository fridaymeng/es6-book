### Variables and scoping

#### let

let works similarly to var, but the variable it declares is block-scoped, it only exists within the current block. var is function-scoped.

```js
function order(x, y) {
  if (x > y) {
    // (A)
    let tmp = x
    x = y
    y = tmp
  }
  console.log(tmp === x) // ReferenceError: tmp is not defined
  return [x, y]
}
```

#### const

const works like let, but the variable you declare must be immediately initialized, with a value that can’t be changed afterwards.

````js
const foo;
// SyntaxError: missing = in const declaration
const bar = 123;
bar = 456;
// TypeError: `bar` is read-only
    ```
````

```js
for (const x of ['a', 'b']) {
  console.log(x)
}
// Output:
// a
// b
```

#### Ways of declaring variables

|          | Hoisting           | Scope         | Creates global properties |
| -------- | ------------------ | ------------- | ------------------------- |
| var      | Declaration        | Function      | Yes                       |
| let      | Temporal dead zone | Block         | No                        |
| const    | Temporal dead zone | Block         | No                        |
| function | Complete           | Block         | Yes                       |
| class    | No                 | Block         | No                        |
| import   | Complete           | Module-global | No                        |

```js
const obj = {}
obj.prop = 123
console.log(obj.prop) // 123
const obj = Object.freeze({})
obj.prop = 123 // TypeError
```

```js
function logArgs(...args) {
  for (const [index, elem] of args.entries()) {
    // (A)
    const message = index + '. ' + elem // (B)
    console.log(message)
  }
}
logArgs('Hello', 'everyone')
// Output:
// 0. Hello
// 1. everyone
```

```js
const arr = []
for (let i = 0; i < 3; i++) {
  arr.push(() => i)
}
arr.map(x => x())
```

```js
const entries = [['yes', 'ja'], ['no', 'nein'], ['perhaps', 'vielleicht']]
for (const [source, target] of entries) {
  console.log(source + '-' + target)
}
```
