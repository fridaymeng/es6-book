### Generators

#### What are generators? 

```js 
function* genFunc() {
    // (A)
    console.log('First');
    yield;
    console.log('Second');
}

const genObj = genFunc();

genObj.next();
// Output: First
genObj.next();
// output: Second

```
Generator function declarations:
```js 
 function* genFunc() { ··· }
 const genObj = genFunc();
```
Generator function expressions:
```js 
const genFunc = function* () { ··· };
const genObj = genFunc();
Generator method definitions in object literals:
const obj = {
     * generatorMethod() {
         ···
     }
};
const genObj = obj.generatorMethod();
```

Generator method definitions in class definitions (class declarations or class expressions):
```js 
class MyClass {
     * generatorMethod() {
         ···
     }
}
const myInst = new MyClass();
const genObj = myInst.generatorMethod();
```
