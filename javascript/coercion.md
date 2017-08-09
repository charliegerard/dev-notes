# Coercion

The conversion of a value between two types.

Example:

```javascript
var a = "42";
var b = Number(a);

console.log(a); // "42"
console.log(b); // 42
```

Using the built-in function `Number()` is an **explicit coercion**.
An **implicit coercion** is when you try to convert two values that are not of the same type. Example: "99" and  99;

JavaScript helps you compare these two values using the `==` **loose equals operator**.
When writing `"99" == 99`, JS will convert the left-hand side to its number equivalent, so the expression will equal *true*.

**Implicit coercion can be confusing.**
