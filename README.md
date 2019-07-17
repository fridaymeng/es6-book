# Introduction

This book is about ECMAScript 6 (whose official name is ECMAScript 2015), a new version of JavaScript.

- In order to understand this book, you should already know JavaScript.

- This book covers ECMAScript 6 in depth.

- This book not only tells you how ES6 works, it also tells you why it works the way it does.

#### Destructive operations

Destructive operations (methods, functions) modify their parameters or their receivers. For example, push() modifies its receiver arr:

```js
const arr = ['a', 'b']
arr.push('c')
console.log(arr)
// ['a', 'b', 'c']
```

In contrast, concat() creates a new Array and does not change its receiver arr:

```js
const arr = ['a', 'b']
arr.concat(['c'])
console.log(arr)
// ['a', 'b']
```

```bash
gitbook serve/build
```
