# Interpreter vs Compiler

#### Interpreter

An interpreter translated code line by line, on the fly.

* Pro: Quick to get up and running. Start running the code as soon as the line has been translated.
* Con: With pieces of code that happen multiple times like loops, interpreters translate the same piece of code again and again. Performance hit.

Interpreter does the work at runtime so can take more time to figure out optimisations.

#### Compiler

Works ahead of time to create the translation and writes it down.

Takes more time to start running the code but then runs faster because it doesn't need to repeat the translation for each time it goes in loops.

Compiler has more time to look at code and make **optimisations** (edits so the code runs faster).

#### Just-in-time compilers

Mix of both.

Browsers added a new part to the JS engine called a **monitor**. It watches the code as it runs and makes notes of how many times it runs, etc...

At first, the monitor runs everything through the interpreter.
If the same lines of code run a few times, the segment of code is called *warm*; if it runs a lot, it's called *hot*.

If a segment starts to get warm, the *JIT* sends it off to the compiler. Then, it will store that compilation.
Each line of the code segment is compiled into a *stub*. Stubs are indexed by line number and variable type. If the monitor sees that execution is hitting the same code again with the same variable types, it will pull out its compiled version.

If a part of the code gets very hot, the monitor will send it off to the **optimising compiler**. This will create an even faster version of the function that will be stored.

---
Source: [https://hacks.mozilla.org/2017/02/a-crash-course-in-just-in-time-jit-compilers/](https://hacks.mozilla.org/2017/02/a-crash-course-in-just-in-time-jit-compilers/)
