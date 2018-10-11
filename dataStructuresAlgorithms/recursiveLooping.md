# Recursive looping

Here's an example of computing a factorial using a for loop in JavaScript:

```javascript
function computeFactorial(num){
  var result = 1;

  for(var i = 2; i <= num; i++){
    console.log(`result of ${result} * ${i} is ${result * i}`)
    result *= i;
  }
}

computeFactorial(num);
```

Recursive loop:

```javascript
function computeFactorialRecursively(num){
  if(num === 1){
    return 1;
  } else {
    return num * computeFactorialrecursively(num - 1);
  }
}

computeFactorialRecursively(5);
```
