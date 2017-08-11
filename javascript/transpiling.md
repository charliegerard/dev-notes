# Transpiling

When trying to adapt new features in JS to older browsers, we can use polyfills. However, when talking about new syntax, the better option is to use a tool that converts the newer code into older code equivalents.

Example with ES6 **default parameter value**:

```javascript
function foo(a = 2){
  console.log(a);
}

foo() // 2;
foo(42) // 42;
```

This syntax is invalid in pre-ES6 engines, so a transpiler will convert it to code that can run in older environments:

```javascript
function foo(){
  var a = arguments[0] !== (void 0) ? arguments[0] : 2;
  console.log(a);
}
// void 0 is the equivalent of undefined
```

Babel is a great transpiler.
