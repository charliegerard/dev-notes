# Hoisting

Hoisting is a way of thinking about how the execution context works in JavaScript.
The variable and function declarations are put into memory during the compile phase but stay where you typed them in your code.

One advantage of JavaScript putting function declarations into memory before executing any code segment is the ability to use a function before it is initialised in your code.

Example:

```javascript
foo();

function foo(){
  console.log('hello world');
}
```

Works the same way as:

```javascript
function foo(){
  console.log('hello world');
}

foo();
```

Hoisting also works with variables. A variable can be initialised and used before it is declared. However, they cannot be used without initialisation.

Ex:

```javascript
num = 1;
num + 7;
var num;
```

The code above does not raise any error.
JavaScript hoists function declarations but not initialisations. If you are using a variable that is declared and initialised after using it, it will return undefined.

```javascript
var x = 1;
console.log(x + " " + y); // y is undefined.
var y = 2;

// This is the same as

var x = 1;
var y;
console.log(x + " " + y);
y = 2;
```
