# Debugging in Node.js

To enter debugging mode in Node.js in the command line, use the `inspect` command like this:

```javascript
node inspect app.js
```

Once inside debugging mode, you can write:

## Navigation commands:

`list()` in which you pass the number of lines you want to see.

```bash
list(10)
```

`n` to execute the next line:

```
n
```

`c` to continue on until the program completes.

```bash
c
```

## Debugging:

Once in debug mode, we can use `repl` to read, eval, print and loop. Inside `repl` mode, we can check the status of our variables.


We can also write `debugger` in our Node.js file to start the debugger at a specific place in our file.

Example:

```javascript
var person = {
  name: "Charlie"
}

person.age = 28

debugger;

person.name = "George";
```

## Debugging using Chrome dev tools

To start debugging your Node.js app in the Chrome dev tools, type the following command in the command line:

`node --inspect-brk app.js`

Then, open a new tab in Chrome, enter `chrome://inspect` and click on the link *Open Dedicated DevTools for Node.js*.
