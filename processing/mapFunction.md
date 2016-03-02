# Using the Map function

In Processing, you can use the map function to convert an input value that is usually between a certain range, to another value between a new range.

The map function takes 5 arguments:

* The input value (the one you want to convert);
* The minimum that value could have.
* The maximum that value could have (the end point of the range).
* The start of the new range we want our value to be in.
* The end of the new range we want our value to be in.

For example, if we want to use the x position of the mouse to impact the color of an ellipse within the width of a sketch, we would use the map function that way:

```
int grey = map(mouseX, 0, width, 0, 255);
fill(grey);
ellipse(0,0,20,20);
```

The value we use to have the x position of the mouse is `mouseX` which is within the range `0` and `width`. But colors are usually between 0 and 255 so we need to convert the value we get from mouseX to a new range between `0` and `255`.
