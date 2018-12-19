# Spread syntax

In ES6, spread syntax is useful to be able to copy objects without having to use `Object.create`, etc...

```javascript
const person = {
  name: "Charlie"
};

const copiedPerson = { ...person };

//

function list(items){
  return [...items, "boop"];
}

const fullList = list(["beep", "bap"]); // return ["beep", "bap", "boop"];
```
