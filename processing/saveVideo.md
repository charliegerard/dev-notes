# Save Processing animations as video

Saving a Processing animation as video is pretty simple.

See the sketch below:

```processing
int positionX = 0;

void setup(){
  size(400,400, P3D);
}

void draw(){
  background(255);
  translate(positionX, height/2, 0);
  rotateY(0.5);
  noFill();
  box(40);

  positionX += 1;
}
```

This sketch shows a cube moving along the X axis.

To be able to save this animation as video, we need to add the following line at the end of the `draw` function:

```processing
  saveFrame("/output/cube_####.png")
```

This line will save each frame in a folder called `output` and will append a number to the name of the file incrementally (ex: 'cube_0001.png', 'cube_0002.png', etc...).

Once these files have been created, in the menu bar, go to `Tools > Movie Maker` and indicate the path to your output folder, the size of your animation and click `Create movie`.
