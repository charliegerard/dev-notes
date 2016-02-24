# How to read resistors.

As its name indicates, resistors resist the flow of electricity going through.

![resistors](https://store.arduino.cc/bmz_cache/a/aa71199ac02d8b3e872b6a42f4fbb13e.image.447x354.jpg)

For example, to light up an LED using an Arduino, we need to use a resistor to let the right amount of electricity go through to control the brightness of the LED.

The unit of resistance is called Ohm or Ω, the Greek letter Omega. However, this is a low value of resistance so for resistors we also have kilo-ohms and mega-ohms (kΩ: 1,000Ω & MΩ 1,000,000Ω);

Resistors seem to look the same, but if you look closely, you can see 3 colored stripes in the middle part that indicate its level of resistance. Each color has a specific number:

* Black	0
* Brown	1
* Red	2
* Orange	3
* Yellow	4
* Green	5
* Blue	6
* Purple	7
* Gray	8
* White	9

The first 2 stripes indicate the first 2 digits of the value. The 3rd stripe indicates the number of zeros after the digits.

For example: Orange, Yellow, Purple would equal to 340 000 000Ω or 340MΩ.

The higher the amount of resistance the less bright the LED will be because less current is let through.

To calculate the amount of resistance needed for your components, there is a formula:

```
R = (VSupply - VForward) / I
```

R is for Resistance, VSupply is for the voltage supplied by the power source (your Arduino for example), VForward is for the voltage needed by your component and I is the current needed by your component.

To power an LED for example, it would be:

(5V - 2V) / 0.03A = 100Ω
