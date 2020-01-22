### Promises for asynchronous programming

The following function returns a result asynchronously, via a Promise:
```js
function asyncFunc() {
    return new Promise(
        function (resolve, reject) {
            ···
            resolve(result);
            ···
            reject(error);
        });
}
```

You call asyncFunc() as follows:
```js
asyncFunc()
.then(result => { ··· })
.catch(error => { ··· });
```

Chaining then() calls
```js
asyncFunc1()
.then(result1 => {
    // Use result1
    return asyncFunction2(); // (A)
})
.then(result2 => { // (B)
    // Use result2
})
.catch(error => {
    // Handle errors of asyncFunc1() and asyncFunc2()
});
```