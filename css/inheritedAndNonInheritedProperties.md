# Inherited and Non-Inherited Properties

Inheritance controls what happens when no value is specified for a property on an element.

## Inherited properties

When no value for an inherited property has been specified on an element, the element gets the **computed value** (value transferred from parent to child during inheritance) of that property on its parent element.

An example of inherited property is the **color** property

```css
p{ color: green; }
```

```html
<p>This paragraph has <em>emphasized text</em></p>
```

The words "emphasized text" will appear green, since the *em* element has inherited the property *color* from its parent element.

---

## Non-inherited properties

When no value for a non-inherited property has been specified on an element, the element gets the **initial value** of that property on its parent element.

Example of non-inherited property: **border**

```css
p{ border: medium solid; }
```

```html
<p>This paragraph has <em>emphasized text</em> in it.</p>
```

The words "emphasized text" will not have a border.


[Source](https://developer.mozilla.org/en-US/docs/Web/CSS/inheritance)
