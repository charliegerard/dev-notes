# this

To understand what `this` is refering to, we need to know the **call-site**, the location where a function was called (not where it was declared).

What's also important is the **call-stack**, the stack of functions that have been called to get us to the current moment in execution.

```javascript
function baz(){
    //call-stack is baz.
    bar(); //call-site for `baz`
}

function bar(){
    //call-stack is: `baz` -> `bar`
    foo() // call-site for `foo`
}

function foo(){
    //call-stack is: `baz` -> `bar` -> `foo
}

baz() //call-site for `baz`
```

The `call-site` of a function is the only thing that matters in understanding the meaning of `this`.

## 4 rules

#### Default binding
---

Let's look at the following example:

```javascript
function foo(){
    console.log(this.a);
}

var a = 2;

foo() // 2;
```
The variable `a` is declared on the global scope. The call-site of the function `foo` is also the global scope, however, `this.a` inside `foo` refers to the variable declared, so returns the value 2. 

#### Implicit binding
---

```javascript
function foo(){
    console.log(this.a);
}

var obj = {
    a: 2,
    foo: foo
}

obj.foo(); // 2;
```

In this example, `foo` is added as a **reference property** onto `obj`.
As the *call-site* of `foo` uses the `obj` context, the *implicit binding* rule applies and `this` refers to the `obj` object.
In that case, `this.a` refers to the `a` property of the `obj` object.


#### Explicit binding
---

```javascript
function foo(){
    console.log(this.a);
}

var obj = {
    a: 2
}

foo.call(obj); //2
```

Using `.call()` forces the `this` to be binded to `obj` passed into `foo.call()`.

A more common way of using this *explicit binding* pattern is by using `bind()`

```javascript
function foo(smthg){
    console.log(this.a, smthg);
    return this.a + smthg;
}

var obj = {
    a: 2
}

var bar = foo.bind(obj);

var b = bar(3); // 2 3
console.log(b) // 5
```

#### `new` binding
---

Using the `new` operator in front of the name of a function in JavaScript does a *constructor call*. The newly constructed object is set as the `this` binding for that function call.

```javascript
function foo(a){
    this.a = a;
}

var bar = new foo(2);
console.log(bar.a); // 2
``` 