# Pure functions

A pure function is a function that always returns the same result when given the same arguments, without side effects.

Example:

```javascript
function double(x){
  return x * 2;
}
// Will always return 4 when x is 2.
// Will always return 8 when x is 4, etc...
```

```javascript
function randomise(y){
  return y * Math.random();
}
// Not a pure function because Math.random() always returns a different number.
```
