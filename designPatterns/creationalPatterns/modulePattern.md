# Module pattern

The module pattern allows to declare both public and private methods and variables inside a single object, shielding particular parts of an object.

Example:

```js
var counting = (function(){
  var counter = 0;

  return {
    incrementCounter: function(){
      return counter++;
    },

    decreaseCounter: function(){
      return counter--;
    }
  }
})();

counting.incrementCounter();

counter.decreaseCounter();
```

In the example above, other parts of the code are not able to read the value returned from `incrementCounter` and `decreaseCounter`.


## Advantages

Supports private data. Public parts of our code are able to touch private parts, however, the outside world is unable to touch the class' private parts.

## Disadvantages

* We can't access private parts in methods that are added to the object later on.

* Automated unit tests for private members is not possible.
