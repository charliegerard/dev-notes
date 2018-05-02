# Type introspection

Inspecting an instance to find out *kind* of object it is.

Example: `instanceof` or `isPrototypeOf`

```javascript
var Foo = { ... }

var Bar = Object.create(Foo);

var b1 = Object.create(Bar);

Foo.isPrototypeOf(Bar); // true
Object.getPrototypeOf(Bar) === Foo; // true

Foo.isPrototypeOf(b1); //true
Bar.isPrototypeOf(b1); //true
```

`instanceof` can be confusingly pretending to have something to do with classes.

Other type of *type introspection* is called **duck typing**.

```javascript
if(a1.something){
  a1.something();
}
```

Here, we assume that the test for `a1.something` passing means `a1` has the capability to call `.something()` (regardless of it being found directly on `a1` or delegated to some other object).

However, *duck typing* is sometimes used for other assumptions - ES6 Promises.

The test is done to check if an object happens to have a `then()` function present on it. If you have any non-Promise object that happens to have a `then()` on it, keep away from the ES6 Promise mechanism.
