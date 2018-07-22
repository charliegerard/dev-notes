# The Web Storage API

**The Web Storage API provides a secure way to store key/value pairs in the browser.**

Storage objects are like normal objects with key/value pairs but they **stay intact through page loads**.

The keys and values are always strings. The integer keys will be automatically converted to strings.

You can access the items of an object with `Storage.getItem()` and `Storage.setItem()`.

There are 2 mechanisms in Web Storage:

* **sessionStorage**: keeps a separate storage area for the duration of the session (until you close the browser).

* **localStorage**: same thing but persits even when the browser is closed and reopened.

They are available via `Window.sessionStorage` and `Window.localStorage`.

#### Setting key/value pairs:

```javascript
localStorage.color = '#000000';
localStorage['color'] = '#000000';
localStorage.setItem('color') = '#000000';
```

`setItem` is used both for creating new data and updating existing one.

#### Getting values:

```javascript
localStorage.getItem('color');
```

#### Storage changes:

A `StorageEvent` is fired whenever a change is made to the storage object. This does not work on the page making the change but works on other pages, in the same domain, sharing the same storage object.

```javascript
window.addEventListener('storage', e => {
  console.log(e.key);
  console.log(e.oldValue);
  console.log(e.newValue);
})
```

#### Deleting data records

* `Storage.removeItem()` - takes the key as argument and deletes the key/value pair.
* `Storage.clear()` - empties the entire storage object.
