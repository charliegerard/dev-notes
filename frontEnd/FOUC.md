# Flash of Unstyled Content or FOUC

Flash of Unstyled Content is an instance when a webpage appears briefly with the browser's default styles prior to loading the CSS stylesheet. due to the browser engine rendering the page before all information is retrieved.

According to Paul Irish's blog, a way to prevent FOUC from happening is to add a `no-js` class to the html element of your page and change this class to `js` if javaScript is loaded.

```html
<html class="no-js">
<head>
  <script>(function(H){H.className=H.className.replace(/\bno-js\b/,'js')})(document.documentElement)</script>
```

What the JavaScript line is doing here is basically this:

```javascript
document.documentElement.className = document.documentElement.className.replace(/\bno-js\b/,'js');
```

You can then define specific CSS for the users with the `no-js` class.
