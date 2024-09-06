ES6 introduced Arrow Functions Syntax. It is a shorter way to write functions by using the special "fat arrow" notation.

```js
() => 
```

Functions that dont have parameters:
```js
const functionName = () => {};
```

Functions that take only **a single parameter** do not need that parameter to be encolsed in parentesis:

```js
const functionName = paramOne => {};
```

Functions that have two or more parameters needs the parentheses:
```js
const functionName = (paramOne, paramTwo) => {};
```

Function bodys that are composed by a single-line block not need curly braces. The contents of the block should immediately follow the arrow and the `return` keyword can be removed. This is referred to as _implicit return_:

```js
const sumNumbers = number => number + number;
```
