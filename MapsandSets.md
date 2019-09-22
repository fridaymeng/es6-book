### Maps and Sets
#### Maps

The keys of a Map can be arbitrary values:
```js
// 有序的键值对
const map = new Map(); // create an empty Map
const KEY = {};

map.set(KEY, 123);
map.get(KEY)
// 123
map.has(KEY)
// true
map.delete(KEY);
// true
map.has(KEY)
// false
```

You can use an Array (or any iterable) with [key, value] pairs to set up the initial data in the Map:
```js
const map = new Map([
    [ 1, 'one' ],
    [ 2, 'two' ],
    [ 3, 'three' ], 
    // trailing comma is ignored
]);
```

#### Sets
A Set is a collection of unique elements:
```js
// 不重复的有序列表
const arr = [5, 1, 5, 7, 7, 5];
const unique = [...new Set(arr)]; 
// [ 5, 1, 7 ]
```

#### WeakMaps/WeakSets


```js
let set = new Set();
let key={};
let key2 = {};
set.add(key);
set.add(key2);
console.log(set.size); 
// 2

key = null;
console.log(set.size); 
// 2
// 弱引用键的对象
const _objToListeners = new WeakMap();

const _proxies = new WeakSet();
```