# Event delegation

Event delegation allows you to avoid adding event listeners to specific nodes but instead add them to a parent.
The event listener analyses bubbled events to find a match on child elements.

Example with a `ul` element with multiple child `li` elements:

```html
<ul id="parent">
  <li id="1">Child one</li>
  <li id="2">Child two</li>
  <li id="3">Child three</li>
  <li id="4">Child four</li>
</ul>
```

We want something to happen when each child element is clicked. We could add an event listener to each child but what if some of these `li` are frequently added and removed from the list?
A better solution is to add the event listener to the parent element and when the event bubbles up to the ul element, you can check the event object's target property to get the actual clicked node.

Example:

```javascript
document.getElementById("parent").addEventListener("click", function(e){
    if(e.target && e.target.nodeName == 'LI'){
      console.log("List item ", e.target.id, " was clicked");
    }
})
```

If we want to target a child element with a specific class, we can also write:

```javascript
document.getElementById("parent-block").addEventListener("click", function(e){
    if(e.target && e.target.matches("a.linkOne")){
      console.log("Link was clicked");
    }
})
```
