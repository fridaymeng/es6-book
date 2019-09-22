### Typed Arrays
<p>
为了在 WebGL 中高效地操作二进制数据，ES6 为浏览器引入了 TypedArray 和 DataView，两个操作底层二进制数据的视图。因为具有直接操作内存的能力而不用进行转换，在处理 WebGL 二进制数据上性能远高于 Array。
</p>
```js
const typedArray = new Uint8Array([0,1,2]);
console.log(typedArray.length); // 3
typedArray[0] = 5;
const normalArray = [...typedArray]; // [5,1,2]

```