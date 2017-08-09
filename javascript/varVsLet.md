# `var` vs. `let`

The difference about `var` and `let` has to do with scope.

Introduced in ES6, `let` allows to declare a variable that is accessible only inside a specific block of code.

Example:

```javascript
function foo(){
  var a = 2;

  if(a > 1){
    let b = 4;

    while(b < 4){
      let c = a + b;
      b++;
    }
  }
}
```

In the example above, `b` can only be accessed inside the *if* statement and not in the whole *foo* function.
Also, `c` can only be accessed inside the *while* loop.
