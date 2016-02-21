# Formula to map out image pixels from two dimensional array to one dimensional array with the raw depth data of the Kinect

We usually think of image pixels as a two-dimensional array of rows and columns. However, computers store these pixels in a one dimensional array.
So when using the depth data of the Kinect with Processing, the formula to map out the pixels in an image is 'x+y*width'.

So to access all the pixels in the image coming from the Kinect and turn them into rectangles representing the brightness, we would write something like this:

```
  int skip = 20;
  for(int x=0; x < img.width; x+=skip){
    for(int y = 0; y < img.height; y+=skip){
      //Formula
      int index = x + y * img.width;
      float b = brightness(img.pixels[index]);
      fill(b);
      rect(x, y, skip, skip);
    }
  }
```
