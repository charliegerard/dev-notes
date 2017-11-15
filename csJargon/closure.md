# Closure

Closure is when a function can access its lexical scope even outside of its lexical scope.

```javascript
function foo(){
  var a = 2;

  function bar(){
    console.log(a) // 2
  }

  return bar;
}

var baz = foo();

baz();
```

In the example above, the function `bar` has access to the inner scope of `foo` and then becomes its return value.

When the variable `baz` is created and is calling the function `foo`, it has access to the inner function `bar`.
This way, `bar` is executed but outside of its declared lexical scope. So even if the inner scope of `foo` should not be accessible anymore, `bar()` still has reference to that scope.
**This is closure.**

More useful example:

```javascript
function wait(message){

  setTimeout(function timer(){
    console.log(message);
  }, 1000);

}

wait("hello world");
```

In the above example, the function `timer()` has access to the inner scope of `wait()` with the reference to the variable `message`.

1000 milliseconds after `wait()` has been called, the inner scope of the function should be gone, however, the inner function `timer` still has access to it, it has **closure over that scope**.

### Loops and closure

```javascript
for(var i = 1; i <= 5; i++){
  setTimeout(function timer(){
    console.log(i);
  }, i * 1000);
}
```
The example above returns five times `6`.

Why?

Because the function `timer()`, even if redefined in each iteration of the loop, has access to a **global scope i**.
By the time `setTimeout` is called, the loop has finished running and the first value of `i` to exit the loop is 6.

For it to print `1 2 3 4 5` we need to define a **closured scope** where there is a new `i` in which iteration of the loop.

The following would work:

```javascript
for(var i = 0; i <= 5; i++){
  (function(){
    var j = i
    setTimeout(function timer(){
      console.log(j);
    }, j * 1000);
  })();
}
```

Because Immediately Invoked Function Expressions (IIFE) create their own block scope every time it's invoked.

Other solution is to use **block scoping** with `let`.

```javascript
for(let i = 1; i <= 5; i++){
  setTimeout(function timer(){
    console.log(i);
  }, i * 1000);
}
```
