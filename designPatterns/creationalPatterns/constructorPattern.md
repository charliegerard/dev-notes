# Constructor pattern

Constructors are used to create specific types of objects.

In JS, an object can be created 3 different ways:

```javascript
var newObject = {};

var newObject = Object.create(Object.prototype);

var newObject = new Object();
```

4 ways to add keys and values to an object:

```javascript
// 1
newObject.newKey = 'hello';

// 2
newObject['newKey'] = 'hello';

// 3
Object.defineProperty(newObject, 'newKey', {
  value: 'hello',
  writable: true,
  enumerable: true,
  configurable: true
})

// 4
Object.defineProperties(newObject, {
  'newKey' : {
    value: 'hello',
    writable: true
  }
});
```

Example of constructor pattern in JS:

```javascript
function Car(year, model){
  this.year = year;
  this.model = model;

  this.toString = function(){
    return this.model + " was released in " + this.year;
  }
}

var delorean = new Car(1975, "DeLorean");

console.log(delorean.toString());
```

The above example makes inheritance difficult and it causes to redefine the function `toString` for every object using the Car constructor. This function should instead be shared by all instances of the Car type.

### Constructors with prototype

```js
function Car(year, model){
  this.year = year;
  this.model = model;
}

Car.prototype.toString = function(){
  return this.model + "was released in " + this.year;
}

var delorean = new Car(1975, "DeLorean");
console.log(delorean.toString());
```

In the above example, the method `toString` will now be shared across all instances of the Car type.
