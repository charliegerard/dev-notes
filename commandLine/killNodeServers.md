# How to kill all instances of Node servers

Errors like the following mean that the port you're currently running is already in use:

```
Error: bind EADDRINUSE
```

To fix this, you can either figure out what is running on the same port and kill only this instance, or decide to kill all node servers. To do this, run the following command in your terminal:

```
killall node
```

All node servers should be stopped and you should be able to restart the ones you need.
