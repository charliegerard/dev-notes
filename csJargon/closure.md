# Closure

Closure represents when a function accesses a variable even outside of its lexical scope.

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
