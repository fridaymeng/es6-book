### Arrow functions

```js
const arr = [1, 2, 3]
const squares = arr.map(x => x * x)

// Traditional function expression:
const squares = arr.map(function(x) {
  return x * x
})
```

```js
function UiComponent() {
  const button = document.getElementById('myButton')
  button.addEventListener('click', () => {
    console.log('CLICK')
    this.handleClick() // lexical `this`
  })
}
```

```js
const func6 = (
  // OK
  x,
  y
) => {
  return x + y
}
```
