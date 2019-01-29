# CSS Specificity

**How browsers decide which CSS property values should be applied on an element.**
A weight that is applied to a given CSS declaration.

Universal selectors (`*`), combinators(`+`, `>`, `~`, `' '`) and negation pseudo-class(`:not()`) have no effect on specificity.

Inline styles added to an element always overwrite any styles given in an external stylesheet. They have **highest specificity**.

The `!important` rule overrides any other declarations.

Styles for a directly targeted element will aways take precedence over inherited styles.

```css
#parent {
  color: green;
}

h1{
  color: purple;
}
```

```html
<html>
  <body id="parent">
    <h1>Here is a title!</h1>
  </body>
</html>
```

The h1 will be purple.

---

### **As per CSS rules, directly targeted elements will always take precedence over rules which an element inherits from its ancestor.**

## Calculating the specificity of a selector

The specificity of a selector can be represented as a 3 digits string with a hyphen.
* 1st digit represents the number of IDs
* 2nd digit representes number of classes
* 3rd digit represents number of type selectors

```css
#red.blue // 1-1-0

#green // 1-0-0

div.yellow#red // 1-1-1

.red.blue.yellow // 0-3-0
```

In the example above, we start from the right, to the left and if we compare `div.yellow#red` and `red.blue.yellow`, the former has a higher specificity.
