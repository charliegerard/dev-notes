# Web Workers

JavaScript is a single-threaded language, so only one script can be executed at a time.
You can use techniques like setTimeout() or setInterval() to try to mimic concurrency but non-blocking techniques are not real concurrency.
You can also try to use Asynchronous promises but they are processed after the current script has finished running.

Web Workers allow you to run script in the background so you can actually have some kind of multi-threading, and handle requests without blocking the UI for example.

[More info](http://www.html5rocks.com/en/tutorials/workers/basics/)
