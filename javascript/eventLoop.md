# JavaScript Event Loop - How do you even?

Based on [awesome talk by Philip Roberts](https://www.youtube.com/watch?v=8aGhZQkoFbQ) and this [Medium article](https://medium.com/@gaurav.pandvia/understanding-javascript-function-executions-tasks-event-loop-call-stack-more-part-1-5683dea1f5ec)

JavaScript is a **single-threaded** **single concurrent** language -> can only execute one task at a time, one piece of code at a time.

**Single call-stack** + heap + queue = **Concurrency Model**

![Visual representation of JS Model](https://cdn-images-1.medium.com/max/1600/1*ZSFHnq9iMHIApVLcgwczPQ.png)

### 1) Call-stack:
Data structure that records the function calls as a stack of *frames*.
When a function is called, it is pushed onto the stack and when it returns, it is popped off the stack.

![JS Stack visualization](https://cdn-images-1.medium.com/max/1600/1*E3zTWtEOiDWw7d0n7Vp-mA.gif)

In the above gif, we can see that we start by adding the `console.log(bar(6))` to the stack because this is where the function is called first.
`bar` is then added onto the stack which calls `foo`.
When `foo` returns, it is popped off the stack and same for `bar` afterwards.

#### Stack trace

When an error happens, the stack trace can be viewed in the browser console. It indicates where we were in the call stack when the error happened.


**The limit size of the stack trace is 16,000 frames.**

---
### 2. Heap

Memory where objects are added and allocated.

---
### 3. Queue

The JavaScript runtime contains a **message queue**, a list of messages to be processed and callback functions to execute.
When the stack is empty, the event loop will take messages from the callback queue and add them onto the call stack to be executed.

![JS Event Loop](https://cdn-images-1.medium.com/max/1600/1*-MMBHKy_ZxCrouecRqvsBg.png)

---

#### setTimeout

The `setTimeout` function is usually called with 2 arguments, a message to add to a queue and a time value in milliseconds. This time value represents the minimum delay after which the message will be executed.
However, if there are already messages in the queue, the delay will be more than the time value indicated as it will have to wait for the other messages to be executed first. 