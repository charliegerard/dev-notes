# Programming paradigms

Ways of programming (patterns, styles, etc...).

Examples:

* Imperative programming
* Declarative programming
* Object-oriented programming
* Functional programming, etc...

### Imperative programming

 Imperative programs spend lines of code describing the specific steps used to achieve the desired results – the flow control, how to do things.

 ### Declarative programming

 Declarative programs abstract the flow control process, and instead spend lines of code describing the data flow: what to do.

Examples:

* Imperative mapping

```javascript
  const doubleMap = numbers => {
    const doubled = [];
    for(var x = 0; x < numbers.length; x++){
      doubled.push(numbers[x] * 2);
    }
    return doubled;
  }
  console.log(doubleMap([2,3,4]));
```

* Declarative mapping:

```javascript
  const doubleMap = numbers => numbers.map(n => n * 2);
  console.log(doubleMap([2,3,4]));
```

The declarative program abstracts the flow control using the functional `map()` function.
