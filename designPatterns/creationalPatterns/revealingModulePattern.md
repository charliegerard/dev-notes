# The Revealing module pattern

This module is a variation of the classic module pattern in which all variables and functions are defined in the private scope and an anonymous object is returned, with pointers to the private members we want to make public.

```js
var profile = (function(){
  //private
  var name = "";

  function setName(nameStrg){
    name = nameStrg;
  }

  function getName(){
    console.log("Name: " + name);
  }

  function sayHello(){
    console.log('Hello ' + name);
  }

  //public pointers
  return{
    giveName: setName,
    getName: getName,
    greet: sayHello
  }
})();
```

## Advantages

* Allows syntax of scripts to be more consistent.

* Makes it more clear which members may be accessed publicly.

## Disadvantages

* Public members can't be overriden by a patch if necessary.
