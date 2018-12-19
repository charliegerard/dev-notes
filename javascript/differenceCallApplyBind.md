# Difference between call(), apply() and bind()

In JavaScript, `call()` and `apply()` are both used to invoke the function immediately whereas `bind()` is used when the function is called later. However, that's not the only difference.

## Call

```javascript
var person = {name: "Charlie"};

var intro = function(a,b,c){
  return "I am"  + this.name + " who lives in " + b + ", " + c;
}

console.log(intro.call(person, "Sydney", "Australia"))

// I am Charlie who lives in Sydney, Australia
```

The 1st parameter in `call()` methods sets the value of `this`, which, in this case is our person object.

The rest of the parameters are arguments to the actual function

## Apply

```javascript
var person = {name: "Charlie"};

var intro = function(a,b,c){
  return "I am"  + this.name + " who lives in " + b + ", " + c;
}

var args = ["Sydney", "Australia"]

console.log(intro.apply(person, args))
```

Similar to `call()`, the 1st argument passed to `apply` defined the value of `this`. The difference is that the 2nd parameter of the `apply` method accepts arguments as an array.

## Bind

```javascript
var person = {name: "Charlie"};

var intro = function(a,b,c){
  return "I am"  + this.name + " who lives in " + b + ", " + c;
}

var boundFunction = intro.bind(person);

console.log(boundFunction("Sydney", "Australia"))
```

In this example, we are returning a bound function with the context that will be invoked.

The first parameter to the `bind` method sets the value of `this` in the target function when the bound function is called.

The following parameters are passed as arguments which are appended to the arguments provided to the bound function when invoking the target function.
