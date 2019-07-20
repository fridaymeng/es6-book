# Introduction

This book is about ECMAScript 6 (whose official name is ECMAScript 2015), a new version of JavaScript.

- In order to understand this book, you should already know JavaScript.

- This book covers ECMAScript 6 in depth.

- This book not only tells you how ES6 works, it also tells you why it works the way it does.

## Glossary

#### Strict mode versus sloppy mode

Strict mode is switched on via the following line (which does nothing in ECMAScript versions before ES5):

'use strict';

ES6 modules and classes are implicitly in strict mode.

#### Protocol

A protocol defines interfaces (signatures for methods and/or functions) and rules for using them.

#### Receiver (of a method call)

Given a method call obj.m(···), obj is the receiver of the method call and accessible via this inside the method.

#### Bindings and environments

The ECMAScript spec uses a data structure called environment to store the variables of a scope. An environment is basically a dictionary that maps variable names to values. A binding is an entry in an environment, storage space for a variable.

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
