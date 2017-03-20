# Constructor pattern

A object constructor is used to create specific types of objects, both preparing the object for use and accepting arguments which a constructor can use to set the values of member properties and methods when the object is first created.

JavaScript doesn't support the concept of classes but supports special constructor functions that work with objects.
By using the prefix `new`, we can tell JavaScript to use a function like a constructor.

#### Basic constructors

```javascript
function Computer(model, size, age, price){
  this.model = model;
  this.size = size; // `this` refers to the object created.
  this.age = age;
  this.price = price;

  this.toString = function(){
    return "My computer is a " + this.model + ", is " + this.size + " big, " + this.age + " old and cost me $" + this.price.
  }
}

//Usage

var mac = new Computer("Mac", "15inch", "2 years", 1000);
var pc = new Computer("Chromebook", "13inch", "1 year", 500);

console.log(mac.toString());
console.log(pc.toString());
```

The problem with the above code is that the function `toString` is defined for every new object created. This is not very optimal as we would like to be able to share this function across the objects created with the `Computer` constructor.

#### Constructors with prototypes.

```javascript
function Computer(model, size, age, price){
  this.model = model;
  this.size = size; // `this` refers to the object created.
  this.age = age;
  this.price = price;
}

Computer.prototype.toString = function(){
    return "My computer is a " + this.model + ", is " + this.size + " big, " + this.age + " old and cost me $" + this.price.
  }

//Usage

var mac = new myComputer("Mac", "15inch", "2 years", 1000);
var pc = new myComputer("Chromebook", "13inch", "1 year", 500);

console.log(mac.toString());
console.log(pc.toString());
```

Now a single instance of `toString` is share across multiple objects.
