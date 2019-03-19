# Descendant combinator

The **descendant combinator** is usually represented by a simple white space between two selectors so that the elements matched by the second selectors are only selected if their ancestor is an element matching the first selector.

```css
/* style applied to list elements inside an unordered list with a class of 'my-list' */
ul.my-list li{
  background-color: pink;
}
```



