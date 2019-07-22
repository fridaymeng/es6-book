### Destructuring

#### Object destructuring

```js
const obj = { first: 'Jane', last: 'Doe' }
const { first: f, last: l } = obj
// f = 'Jane'; l = 'Doe'

// {prop} is short for {prop: prop}
const { first, last } = obj
// first = 'Jane'; last = 'Doe'
```

#### Array destructuring

```js
const iterable = ['a', 'b']
const [x, y] = iterable
// x = 'a'; y = 'b'
```

```js
const [all, year, month, day] = /^(\d\d\d\d)-(\d\d)-(\d\d)$/.exec('2999-12-31')
```

```js
const arr = ['a', 'b']
for (const [index, element] of arr.entries()) {
  console.log(index, element)
}
// Output:
// 0 a
// 1 b
```

```js
const [x, y] = ['a', 'b'] // x = 'a'; y = 'b'
```

```js
const arr = ['a', 'b']
const iter = arr[Symbol.iterator]()
while (true) {
  const { done, value } = iter.next() // (A)
  if (done) break
  console.log(value)
}
```
