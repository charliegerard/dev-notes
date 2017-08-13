# Scope

**Scope** can be defined as a set of rules for storing variables in some location and finding these variables later.

 In a program, there is usually **more than one scope**. As functions can be nested, scopes can be nested too. So, if a variable cannot be found in the immediate scope, the JS engine consults the **next outer-container scope** until the variable is found or until the outermost container (global scope) is reached.

 The look-up of variables can have **2 purposes**, **assigning to a variable (left-hand side reference) or retrieving the value of a variable (right-hand side reference)**.

 Example:

 ```javascript
 var a = 2; // The reference to a is a LHS reference as we just want to find the variable as a target for the value 2.

 var b = a; // Here, a is a RHS look-up reference as we need to retrieve the value of a to assign to b;

 console.log(b); // b is a RHS look-up reference as we need to retrieve the value of b;
 ```

We care about knowing the type of look-up as they behave differently where the variable has not been yet declared.

If an RHS look-up fails to find a variable, it will throw a `ReferenceError` whereas if a LHS look-up fails to find a variable, it may create it automatically for us (if `strict mode` is not used).

Example:

```javascript
function foo(a){
  // console.log(a + b);
  b = a;
}

foo(2);
```

In the above example, `b` is a LHS look-up and cannot be found even in the global scope but this won't generate any error as the global scope will create the variable for us.
