# Rest syntax

Rest syntax is the inverse of spread syntax. It is taking data and putting it into an array.

```javascript

function addOne(...numbers){
  return numbers.map(n => n + 1);
}

const foo = addOne(1,2,3,4,5); // [1,2,3,4,5]

const [a,b,...rest] = [1,2,3,4] // a: 1, b: 2, rest: [3,4]
```
