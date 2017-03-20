# Module pattern

In JavaScript, the Module pattern is used to emulate the concept of classes in such ways that we're able to include both public and private methods and variable inside a single object.

```javascript
var testModule = (function(){
  var counter = 0;

  return {
    incrementCounter: function(){
      return counter++;
    },

    resetCounter: function(){
      console.log("counter value prior to reset: ", counter);
      counter = 0;
    }
  };
})();

//Usage

testModule.incrementCounter();

testModule.resetCounter();
```

Another way to create a template with public and private variables would be like this:

```javascript
var myNamespace: (function(){
  var myPrivateVar, myPrivateMethod;

  myPrivateVar = 0;

  myPrivateMethod = function(foo){
    console.log(foo);
  }

  return {
    myPublicVar: "bar",

    myPublicFunction: function(bar){
      myPrivateVar++;
      myPrivateMethod(bar);
    }
  };
})();
```

The module itself is totally self-contained under the namespace myNamespace. The private variable and method cannot directly be read by other parts of our application. It only exists with the module's closure and so the only method able to access them is `myPublicFunction`.
