# Class / Prototypal inheritance

In Js, all functions by default get a public property on them called `prototype`.

```javascript
function Foo(){
  // ...
}

Foo.prototype; // { }
```

Each object created from called `new Foo()` will end up `[[Prototype]]`-linked to this object.

```javascript
function Foo(){

}

var a = new Foo();

Object.getPrototypeOf(a) === Foo.prototype; // true
```

When `a` is created by calling `new Foo()`, `a` gets an internal `[[Prototype]]` link to the object that `Foo.prototype` is pointing at.

In JS, there are no copies of a class being made. You can't create multiple instances of a class, you can create multiple objects that `[[Prototype]]` link to a common object.

The objects don't end up totally separate and disconnected to each other, but rather, **linked**.

**In JS, we don't make copies from one object ("class") to another ("instance"). We make links between objects.**

**This mechanism is called Prototypal inheritance.**


## Constructors

Take the following example:

```javascript
function Foo(){
  console.log("hello");
}

var a = new Foo(); // hello;

a; // {}
```

`Foo` is just a normal function, but when called with `new`, it *constructs* an object which we assign to `a`. The **call** was a *constructor call*, but `Foo` is not a constructor.

Functions aren't constructors but function calls are "constructor calls" if `new` is used.

## Object.create()

Using `Object.create()` creates a new object.



