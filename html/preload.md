# Preload

Preload is a new web standard aiming to improve performance. It gives developers the ability to define custom loading logic.

For example, you could use it to load late-discovered resources. Depending on how you write your code to load your resources, your browser may not know it needs to load something until later so you can let it know to load particular resources in advance.

To do so, you would do:

```
<link rel="preload" href="late_discovered_thing.js" as="script">
```

The 'as' attribute tells the browser what will be loaded. It could be:

* "script"
* "image"
* "style"
* "media"
* "document"

You could also load fonts before you need them or anything you'd want to execute later.
For example, if you want to execute a script at a certain point in a page's life, you can do so by injecting it when you want to run it but if you do it that way, the browser will need to load it first before being able to execute it, which can result in delays.
Now, with preload, you can preload the scripts and execute it when you want without having to wait for it to load.

```
var preload = document.createElement("link");
link.href = "myscript.js";
link.rel = "preload";
link.as = "script";
document.head.appendChild(link);
```

Then, when you want to run the script, you just inject it where you want to run it:

```
var script = document.createElement("script");
script.src = "myscript.js";
document.body.appendChild(script);
```

More info: [W3C - Preload](https://www.w3.org/TR/preload/)
