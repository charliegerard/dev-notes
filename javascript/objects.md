# Objects

Objects in JavaScript can have a literal form (`var a = {value: 3}`) or a constructed form (`var a = new Array()`).

Objects are of 6 primitive types:

```
string
number
boolean
null
undefined
object
```

Objects are a collection of key/value pairs. The values can be accessed as properties with `.propName` or `["propName"]`.

Properties have characteristics that can be controlled with **property descriptors** such as `writable`.

```javascript
var myObject = {
	a: 2
};

Object.getOwnPropertyDescriptor( myObject, "a" );
// {
//    value: 2,
//    writable: true,
//    enumerable: true,
//    configurable: true
// }
```

Objects can have their mutability modified using `Object.freeze(..)` or `Object.seal(..)`.

Properties don't have to hold a value, they can be **accessors properties** with getters/setters.
