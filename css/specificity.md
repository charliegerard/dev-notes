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
