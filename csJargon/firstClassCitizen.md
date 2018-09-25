# First-class citizen

A first-class function is a function that can be treated like any other variable.

==> A function can be passed as an argument to another function, can be returned by a function and can be assigned as a value to a variable.

### Passing function as value
```javascript
const square = function(x){
  return x * x;
}

square(5); //25
```

### Passing function as argument

```javascript
function sayHello(){
  return "Hello ";
}

function greeting(message, name){
  console.log(message() + name);
}

greeting(sayHello, "World");
```

### Returning a function

```javascript
function sayHello(){
  return function(){
    console.log("hello ");
  }
}

const foo = sayHello();
foo() // hello;
// or
foo()();
```


