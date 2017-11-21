# Difference `null`, `undefined`, `undeclared`


A variable is said to be `undeclared` when you are trying to use it before you even declare it - it doesn't exist.

```javascript
console.log(a); //ReferenceError: a is not defined
```

`null` is a value given to a variable to indicate that it is empty.

```javascript
var a = null;
console.log(a); // null
```

A variable is `undefined` when it is used but does not have a value.

```javascript
var a;
console.log(a); // undefined
```

