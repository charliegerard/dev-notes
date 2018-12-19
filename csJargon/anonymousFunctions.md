# Anonymous functions

**Function that is declared without any named identifier. Therefore it is not accessible after its initial creation.**

Example:

```javascript
function(){
  console.log('boo')
}
```

## Use case

Anonymous functions can be used for **IIFE (Immediately Invoked Function Expressions)** to encapsulate some code inside a local scope so that variables declared in it do not leak to the global scope.

```javascript
(function(){
  console.log('hello')
})();
```

They can also be used as **callbacks**:

```javascript
setTimeout(function(){
  console.log('hello')
}, 1000);
```
