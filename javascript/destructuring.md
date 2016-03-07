# Array destructuring

Destructuring is an assignment syntax in JS that allows to extract data from arrays using a syntax that mirrors the construction of array or object literals.

Example:

```
var a, b;
[a, b] = [1, 2];
//a is equal 1 and b equals 2;
```

Array destructuring example:

```
var foo = ["one", "two", "three"];
//with destructuring;
var [one, two, three] = foo;
/*
this is equivalent to:
var one = foo[0];
var two = foo[1];
var three = foo[2];
*/
```
