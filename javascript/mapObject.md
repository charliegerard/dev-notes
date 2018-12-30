# The Map() object

The `Map` object has key-value pairs and remembers the original insertion order of the keys.

It differs from the normal `Object` because:

* Any values can be used as a key or value. (In `Object`, keys have to be Strings or Symbols).
* The keys in `Map` are ordered, so iterating over the object will return the keys in order of insertion.
* Using the `size` property on a `Map` will return the size of a Map.
* `Map` objects are iterable.

Example:

```javascript
const cities = new Map([
  [0, 'Paris'],
  [1, 'London'],
  [2, 'Sydney']
])

for (var value of cities.value()){
  console.log(value)
}
```

or

```javascript
var cities = new Map()

cities.set('0', "Paris");
cities.set({}, "London");
cities.set(() => {}, "Sydney");

for (var [key, value] of cities.entries()) {
  console.log(key + ' = ' + value);
}

// 0 = Paris
// [object Object] = London
// () => {} = Sydney
```
