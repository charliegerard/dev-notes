# Implicit shadowing


```javascript
var anotherObject = {
  a: 2,
  foo: "boo"
}

var myObject = Object.create(anotherObject)

myObject.foo = "bar"
```

`myObject` is an object **[[Prototype]] linked** to `anotherObject`.

myObject doesn't actually exist.

If the property `foo` is present on `myObject` but not higher in the chain, `foo` is added directly to `myObject`.
However, if `foo` is present on both `myObject` and higher in the prototype chain, it is called **shadowing**.
The `foo` property on `myObject` shadows any `foo` that appears higher in the chain.

Setting `myObject.foo = "bar"` when `foo` is not already directly on `myObject` but is at a higher level in the chain can result in 3 things:

* If `foo` is found at a higher level of the prototype chain and is not marked as read-only (writable:true), a new property is added directly to `myObject`, resulting in a **shadowed property**.

* If `foo` is found higher but is read-only (writable:false), both setting that existing property and the creation of the shadowed property are disallowed.

* If `foo` is found and it's a setter(*), then the setter will always be called. No `foo` will be added to `myObject`.

* setter reminder:

```javascript
  var anotherObject: {
    set foo: {
      return "boo"
    }
  }
```

If we want to shadow `foo` in case 2 and 3, we need to use `.defineProperty()` to add `foo` to `myObject`.


Be careful with shadowing:

```javascript
var anotherObject = {
	a: 2
};

var myObject = Object.create( anotherObject );

anotherObject.a; // 2
myObject.a; // 2

anotherObject.hasOwnProperty( "a" ); // true
myObject.hasOwnProperty( "a" ); // false

myObject.a++; // oops, implicit shadowing!

anotherObject.a; // 2
myObject.a; // 3

myObject.hasOwnProperty( "a" ); // true
```

You could think that `myObject.a++` increments the `anotherObject.a` by looking-up the chain but the operation corresponds to `myObject.a = myObject.a + 1`.

[[Get]] looks up the property `a` via `[[Prototype]]` to get the value 2, then `[[Put]]` assigns the value 3 to a new shadowed property `a` on `myObject`.

---

*Notes summarized from [here](https://github.com/getify/You-Dont-Know-JS/blob/master/this%20%26%20object%20prototypes/ch5.md)*
