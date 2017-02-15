# AMD - Asynchronous Module Definition

AMD's goal is to provide a solution for modular JavaScript.
AMD's format allows both the module and dependencies to be asynchronously loaded.

Two key concepts are the `define` method for facilitating module definition and the `require` method for handling dependency loading.

`define` is used to define named or unnamed modules using the following format:

```javascript
  define(
      module_id /*optional*/,
      [dependencies] /*optional*/,
      definition function /*function for instantiating the module or object*/
  );
```

The *dependencies* argument is an array of dependencies which are required by the module and the *define function* is a function that's executed to initiate your module.

Example:

```javascript
  define('myModule',
    ['one', 'two'],
    function (one, two){
      var myModule = {
        doSomething: function(){
          console.log('hello');
        }
        return myModule;
      }
    }
  )
```

*require* works as follows:

```javascript
// one and two are two external modules
require(['one', 'two'], function (one, two ) {
        // rest of your code here
        one.doSomething();
});
```

Dynamically-loaded dependencies:

```javascript
define(function(require){
  var isReady = false, oneTwo;

  require(['one', 'two'], function(one, two){
    isReady = true;
    oneTwo = one() + two();
  })

  return{
    isReady: isReady,
    oneTwo: oneTwo
  }
})
```

Loading AMD modules using RequireJS:

```javascript
require('app/myModule', function(myModule){
  var module = new myModule();
  module.doSomething();
})
```
