# The stacking context

The stacking context is a **three-dimensional conceptualisation of HTML elements along an imaginary z-axis relative to the user.**

The rendering order of certain elements is influenced by using their z-axis property.

Within a stacking context, the z-axis of its child elements only has meaning in its parent.

Example:

![stacking context](https://developer.mozilla.org/@api/deki/files/913/=Understanding_zindex_04.png)

In the example above, all divs have their own stacking context because of their positioning and z-index value.

## Stacking without the z-index property

When z-index is not specified on an element, elements are stacking in the following order:

* The background and borders of the element
* Descendant non-positioned blocks in order of appearance in the HTML
* Descendant positioned elements in order of appearance in the HTML
