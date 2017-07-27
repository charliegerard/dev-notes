# Feature Queries

Feature queries in CSS are a tool to detect the availability of a feature in CSS.

Using `@support`, you can write a little test to see if a "feature" is supported and apply any block of code (or not) depending on the result.

Example:

```CSS
@supports(display: grid){
  // Code that will run if CSS grids are supported.
}
```

Other tools like Modernizr do the same thing as feature queries, but they use JavaScript.

#### When to use @supports?

Some browsers do not support properties like `border-radius` for example. However, testing if this feature is available is **not really necessary**. **Feature queries** are here to bundle CSS declarations so that they'll **run as a group under a certain condition**.

Example:

The property `initial-letter` tells the browser to render the element bigger. Here, we tell it to be the size of 4 lines but also to be orange and bold.

```CSS
p::first-letter {
  -webkit-initial-letter: 4;
  initial-letter: 4;
  color: #FE742F;
  font-weight: bold;
  margin-right: 0.5em;
}
```

However, in some browsers, `initial-letter` is not supported, so the 1st letter will be bold and orange but not bigger from the rest of the text, which is not what we want. This is where we can use feature queries to check if `initial-letter` is supported before applying the whole block of CSS.

```CSS
@supports (initial-letter: 4) or (-webkit-initial-letter: 4) {
  p::first-letter {
     -webkit-initial-letter: 4;
     initial-letter: 4;
     color: #FE742F;
     font-weight: bold;
     margin-right: 0.5em;
  }
}
```

This way, if the feature is supported, the letter will appear bigger, orange and bold, and if it's not supported, it will appear like the rest of the text.

<a href="https://hacks.mozilla.org/2016/08/using-feature-queries-in-css/" target="_blank">More info</a>
