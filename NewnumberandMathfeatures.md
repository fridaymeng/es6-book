### New number and Math features

```js
> 0xFF // ES5: hexadecimal
255
> 0b11 // ES6: binary
3
> 0o10 // ES6: octal
8
```

```js
> Number.isInteger(1.05)
false
> Number.isInteger(1)
true

> Number.isInteger(-3.1)
false
> Number.isInteger(-3)
true
```

```js
Number.isSafeInteger(number)
Number.MIN_SAFE_INTEGER //-9007199254740991
Number.MAX_SAFE_INTEGER //9007199254740991
```

```js
> isNaN('???')
true
> Number.isNaN('???')
false
```

Math.sign() returns the sign of a number:

```js
//返回正负数
Math.sign(-8)
//- 1
Math.sign(0)
//0
Math.sign(3)
//1
```

Math.trunc() removes the decimal fraction of a number:

```js
//将数字的小数部分去掉，只保留整数部分。
> Math.trunc(3.1)
3
> Math.trunc(3.9)
3
> Math.trunc(-3.1)
-3
> Math.trunc(-3.9)
-3
```

Math.log10() computes the logarithm to base 10:

```js
//对数
> Math.log10(100)
2
```

Math.hypot() Computes the square root of the sum of the squares of its arguments (Pythagoras’ theorem):

```js
> Math.hypot(3, 4)
5
```

#### New integer literals

ECMAScript 6 brings two new kinds of integer literals:

- Binary literals have the prefix 0b or 0B:

```js
//二进制
> 0b11
3
> 0b100
4
```

- Octal literals have the prefix 0o or 0O (that’s a zero followed by the capital letter O; the first variant is safer):

```js
//八进制
> 0o7
7
> 0o10
8
```

Remember that the Number method toString(radix) can be used to see numbers in a base other than 10:

```js
> 255..toString(16)
'ff'
> 4..toString(2)
'100'
> 8..toString(8)
'10'
```

#### Use case for octal literals: Unix-style file permissions

In the Node.js file system module, several functions have the parameter mode. Its value is used to specify file permissions, via an encoding that is a holdover from Unix:

##### Permissions are specified for three categories of users:

- User: the owner of the file
- Group: the members of the group associated with the file
- All: everyone

##### Per category, the following permissions can be granted:

- r (read): the users in the category are allowed to read the file
- w (write): the users in the category are allowed to change the file
- x (execute): the users in the category are allowed to run the file

```bash
000	–––	0
001	––x	1
010	–w–	2
011	–wx	3
100	r––	4
101	r–x	5
110	rw–	6
111	rwx	7
```
