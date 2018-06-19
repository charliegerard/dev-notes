# Abstract syntax tree

Abstract syntax tree or AST is a **way of representing code to convert source code as plain text to a data structure that can then be used to generate bytecode or machine code**.

ASTs can also be used for **static code analyzing**, not in the aim to execute the code but to build tools that can find common code structures that can be refactored for example.

ASTs are also used to implement code transpilers, to transpile code from Python to JS for example. You would use a Python transpiler to generate an AST which would then be used to generate JS code.

```javascript
function foo(){
  if(x > 10){
    var a = 2;
    return a * x;
  }

  return x + 10;
}
```

Here is a simple version of the AST this piece of code will generate:

![AST](https://cdn-images-1.medium.com/max/1600/0*mSOIiWpkctkD0Gfg.)




