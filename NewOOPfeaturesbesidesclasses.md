### New OOP features besides classes

In ECMAScript 5, methods are properties whose values are functions:

```js
var obj = {
    myMethod: function (x, y) {
        ···
    }
};
```

In ECMAScript 6, methods are still function-valued properties, but there is now a more compact way of defining them:
```js
const obj = {
    myMethod(x, y) {
        ···
    }
};
```
Getters and setters continue to work as they did in ECMAScript 5 (note how syntactically similar they are to method definitions):
```js
const obj = {
    get foo() {
        console.log('GET foo');
        return 123;
    },
    set bar(value) {
        console.log('SET bar to '+value);
        // return value is ignored
    }
};
```
There is also a way to concisely define properties whose values are generator functions:
```js
const obj = {
    * myGeneratorMethod() {
        ···
    }
};
This code is equivalent to:

const obj = {
    myGeneratorMethod: function* () {
        ···
    }
};
```

#### Property value shorthands
```js
const x = 4;
const y = 1;
const obj = { x, y };
```
The last line is equivalent to:
```js
const obj = { x: x, y: y };
```

#### Computed property keys

```js
const obj = {
    foo: true,
    ['b'+'ar']: 123
};
```

```js
const obj = {
    * [Symbol.iterator]() { // (A)
        yield 'hello';
        yield 'world';
    }
};
for (const x of obj) {
    console.log(x);
}
```
#### New methods of Object
```js
const obj = { foo: 123 };
Object.assign(obj, { bar: true });
console.log(JSON.stringify(obj));
// {"foo":123,"bar":true}
```

#### Object.is(value1, value2)
```js
> Object.is(NaN, NaN)
true
> Object.is(-0, +0)
false
```

Array method findIndex() to find NaN in Arrays.
```js
function myIndexOf(arr, elem) {
    return arr.findIndex(x => Object.is(x, elem));
}
const myArray = [0,NaN,2];
myIndexOf(myArray, NaN); // 1
myArray.indexOf(NaN); // -1
```
```js
const a = {bdd: 0};
Object.keys(a);
["bdd"]
```
