### Parameter handling

#### Default parameter values

```js
function func(x, y = 0) {
  return [x, y]
}
func(1, 2) // [1, 2]
func(1) // [1, 0]
func() // [undefined, 0]
```

#### Rest parameters

```js
function format(pattern, ...params) {
  return { pattern, params }
}
format(1, 2, 3)
// { pattern: 1, params: [ 2, 3 ] }
format()
// { pattern: undefined, params: [] }
```

```js
> Math.max(-1, 5, 11, 3)
11
> Math.max(...[-1, 5, 11, 3])
11
> Math.max(-1, ...[-5, 11], 3)
11
```
