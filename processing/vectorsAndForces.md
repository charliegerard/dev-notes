# Vectors and Forces

Concepts learnt from reading *The Nature of code* include: Location, Velocity, Acceleration, Gravity and Wind.

Example of bouncing ball with gravity.

Class constructing the bouncing ball:

``` c
class Mover{

  PVector position; //Represents the position of the object;
  PVector velocity; // Represents the speed of that object in a given direction.
  PVector acceleration; // Represents the increase of speed at which the object is moving.
  float mass;
  int colour;

  Mover(float m, float x, float y){
    mass = m;
    position = new PVector(x, y);
    velocity = new PVector(0,0);
    acceleration = new PVector(0, 0);
    colour = 200;
  }

  void applyForce(PVector force){
    //Different forces are applied to an object (ex: gravity, wind and friction).
    //Each of them has to be divided by the mass of the object and then added to its acceleration.
    PVector f = PVector.div(force, mass); //Make a copy of the force vector to not overwrite it.
    acceleration.add(f);
  }

  void update(){        
    velocity.add(acceleration); // The increase of speed is added to the vector representing the movement.
    position.add(velocity); // The movement is applied to the position.
    acceleration.mult(0); //Clearing acceleration for each frame as acceleration is an accumulation of the forces at any given time. If we don't clear the acceleration, it will just increase over time.
  }

  void display(){
    noStroke();
    fill(colour);
    ellipse(position.x, position.y, mass*16, mass*16);
  }

  void checkEdges(){ //Simply checking the edges of the sketch to have a bouncing ball.
    if(position.x > width){
      position.x = width;
      velocity.x *= -1;
    } else if(position.x < 0){
      velocity.x *= -1;
      position.x = 0;
    }

    if(position.y > height){
      velocity.y *= -1;
      position.y = height;
    }
  }
}
```

Main sketch code:

```c
Mover[] movers = new Mover[20]; //Array of 20 bouncing balls.

void setup() {
  size(800, 400);

  for (int i= 0; i < movers.length; i++) {
    movers[i] = new Mover(random(0.1, 4), 0, 0);
  }
}

void draw() {
  fill(0, 10);
  rect(0, 0, width, height);

  for (int i = 0; i < movers.length; i++) {
    PVector wind = new PVector(0.01, 0);
    float m = movers[i].mass;
    PVector gravity = new PVector(0, 0.1*m);

    float c = 0.01; // coefficient of friction, strength of a friction force for a surface;
    float normal = 1; // normal force or gravitational force;
    float frictionMagnitude = c * normal; //Magnitude of friction = gravitational force * strength of friction on surface.

    PVector friction = movers[i].velocity.get(); //Creates a copy of the velocity vector.
    friction.mult(-1); //Friction points in the opposite direction of velocity.
    friction.normalize(); //Makes friction a unit vector.
    friction.mult(frictionMagnitude);

    movers[i].applyForce(friction);
    movers[i].applyForce(wind);
    movers[i].applyForce(gravity);

    movers[i].update();
    movers[i].display();
    movers[i].checkEdges();
  }
}
```

End result:

![](out.gif)
