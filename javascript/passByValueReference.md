# Passing by value of reference in JavaScript

**Depending on the type of variable passed as an argument in a function, JavaScript passes either by value or reference.**

## Passing by value.

If we are passing a **primitive** (string, boolean, number, null, undefined, symbol), **JavaScript passes by value**, which means changing the value of this variable inside the function does not affect the original variabled passed from outside.

```javascript
function change(name){
  name = "Patrick"
  console.log(name)
}

var name = "Charlie"

console.log(name) // Charlie

change(name) // Patrick

console.log(name) // Charlie
```

## Passing by reference.

When the variable passed in a function is an **object or array**, JavaScript passed by **reference**, which means modifying the array/object inside the function is going to change the value of the original variable passed in from outside.

```javascript
function change(details){
  details.name = "Patrick"
  console.log(details.name) // Patrick
}

var details = {
  name: "Charlie"
}

console.log(details.name) // Charlie

change(details) // Patrick

console.log(details.name) // Patrick
```
