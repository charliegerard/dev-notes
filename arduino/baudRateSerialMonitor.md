# Setup the correct baud rate in the Serial Monitor

In Arduino, if you want to print something in the console, you have to use the Serial monitor.

In your code, you usually start by setting the Serial communication in your setup function like this:

```
  void setup(){
    Serial.begin(9600);
  }
```

At first I thought that 9600 was some kind of port, but not at all, it's the data rate in bits per second for serial data transmission.

So when you open your serial monitor, you have to be careful to set the same baud rate in the bottom right dropdown otherwise you'll notice that what you are trying to print in your console does not work properly.

![serial monitor](https://cdn.sparkfun.com/assets/7/f/b/b/2/521fa7f1757b7f63778b456d.jpg)
