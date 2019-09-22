### Iterables and iterators
#### Constructs supporting iteration
Language constructs that access data via iteration:

+ Destructuring via an Array pattern:
```js
  const [a,b] = new Set(['a', 'b', 'c']);
```
+ for-of loop:
```js
  for (const x of ['a', 'b', 'c']) {
      console.log(x);
  }
```
+ Array.from():
```js
  const arr = Array.from(new Set(['a', 'b', 'c']));
```
+ Spread operator (...):
```js
  const arr = [...new Set(['a', 'b', 'c'])];
```
+ Constructors of Maps and Sets:
```js
  const map = new Map([[false, 'no'], [true, 'yes']]);
  const set = new Set(['a', 'b', 'c']);
```
+ Promise.all(), Promise.race():
```js
  Promise.all(iterableOverPromises).then(···);
  Promise.race(iterableOverPromises).then(···);
```
+ yield*:
```js
  yield* anIterable;
```