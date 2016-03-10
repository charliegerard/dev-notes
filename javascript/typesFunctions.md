# Different types of functions

There are different ways of writing a function in JavaScript.

Functions defined with the `Function` constructor assigned to the variable `add`:

```
function add(x, y){
  return x + y;
}
```

A function expression of an anonymous function assigned to the variable `add`:

```
var add = function(x,y){
  return x + y;
}
```

A function expression of a function named func_name assigned to the variable `add`:

```
var add = function func_name(x,y){
  return x + y;
}
```

These 3 ways kinda do the same thing but with a few differences.

There is a difference between the function name and the variable it is assigned to.
The function name cannot change whereas the variable it is assigned to can.
The function name can only be used within the function's body.

For example, the following will throw an error:
```
var y = function x(){};
alert(x);
```

A function declaration also creates a variable with the same name as the function name. However, unlike those defined by function expression, functions defined by function declarations can be accessed by their name in the scope they were defined in.


A function defined by function declaration can be used before the function declaration itself. For example:

```
foo();
function foo(){
  console.log('foo');
}
```

A function declaration is easily turned into a function expression. A function declaration ceases to be one when:

* It becomes part of an expression.
* It is no longer a 'source element' of a function or the script itself. A 'source element' is a non-nested statement in the script or a function body.

Examples:

```
// function declaration
function foo() {}

// function expression
(function bar() {})

// function expression
x = function hello() {}

if (x) {
   // function expression
   function world() {}
}

// function declaration
function a() {
   // function declaration
   function b() {}
   if (0) {
      // function expression
      function c() {}
   }
}
```
