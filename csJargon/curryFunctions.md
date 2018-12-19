# Curry functions

**Currying is the process of breaking down a function into a series of functions that each take a single argument.**

Example without currying;

```javascript
function add(a,b,c){
  return a + b + c;
}

console.log(add(1,2,3));
```
---

Example with currying:

```javascript
function add(a){
  return function(b){
    return function(c){
      return a + b + c;
    }
  }
}
console.log(add(1)(2)(3))

// OR in ES6

const add = x => y => z => x + y + z;
```


## Why use currying?

One reason to use currying is that you can separate when and where your arguments are specified.

For example, you might not have all the arguments ready to be added to call the `add` function right away.

If we don't have all the arguments yet, our `add` function returns a function. We only call the original function when all the arguments are provided.


