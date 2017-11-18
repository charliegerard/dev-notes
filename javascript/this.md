# this

To understand what `this` is refering to, we need to know the **call-site**, the location where a function was called (not where it was declared).

What's also important is the **call-stack**, the stack of functions that have been called to get us to the current moment in execution).

```javascript
function baz(){
    //call-stack is baz.
    bar(); //call-site for `baz`
}

function bar(){
    //call-stack is: `baz` -> `bar`
    foo() // call-site for `foo`
}

function foo(){
    //call-stack is: `baz` -> `bar` -> `foo
}

baz() //call-site for `baz`
```

The `call-site` of a function is the only thing that matters in understanding the meaning of `this`.

### 4 rules

