### Metaprogramming With Proxies
In the following example, proxy is the object whose operations we are intercepting and handler is the object that handles the interceptions. In this case, we are only intercepting a single operation, get (getting properties).
```js
const target = {};
const handler = {
    get(target, propKey, receiver) {
        console.log('get ' + propKey);
        return 123;
    }
};
const proxy = new Proxy(target, handler);
```

When we get the property proxy.foo, the handler intercepts that operation:
```js
> proxy.foo
get foo
123
```