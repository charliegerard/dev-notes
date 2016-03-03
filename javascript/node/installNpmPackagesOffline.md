# Install Npm packages offline

You can now install npm packages while being offline using `local-npm`.
Local-npm is a node server that acts like a local npm mirror. With `local-npm`, your `npm install`s are fetched from the registry and stored in your local PouchDB database.
This way future `npm install`s will use the local cache rather than calling the network.

To install local-npm, run:

```
npm install -g local-npm
```

Then run:

```
local-npm
```

This command will begin the replication process.

To complete the process, you can set npm to point to the local server local-npm is running:

```
npm set registry http://127.0.0.1:5080
```

Now you should be able to run npm install with a module you already have and it will fetch it from your local-npm server.

[More info](https://github.com/nolanlawson/local-npm)
