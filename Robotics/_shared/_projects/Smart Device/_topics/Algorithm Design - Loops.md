---
tag: Robotics
---

![[Theory#Algorithm Design - Loops]]

# Arduino Implementation

The Arduino language has the three loop structures identified on the General Learning Resource - `while`, `do..while` and `for`. As Arduino is a C-based language, the syntax for these are the same as with C, C++ etc.

Here you can see the syntax and an example of each.

## While Loop

```arduino
while (condition) {
  // statement(s)
}
```

### Example

```arduino
var = 0;
while (var < 200) {
  // do something repetitive 200 times
  var++;
}
```

## Do... While Loop

```arduino
do {
  // statement block
} while (condition);
```

### Example

```arduino
int x = 0;
do {
  delay(50);          // slight delay
  x = x + 1;          // add 1 to x.
} while (x < 100);
```

## For Loop

```arduino
for (initialization; condition; increment) {
  // statement(s);
}
```

### Example

```arduino
for (int i = 0; i <= 255; i++) {
	analogWrite(PWMpin, i);
	delay(10);
  }
```

<aside>
‼️ Remember the *condition* has to equate to `true` or `false`.

</aside>

# Practical Exercises

<aside>
🏁 **Goal**

In this task, you’ll be extending the Bank Alarm circuit by adding a number of additional LEDs to be used in a sequence. You will be using loops to access and cycle through the LEDs.

</aside>

Log into [Tinkercad](https://www.tinkercad.com/) and access the classroom used previously. Open the activity `Bank Alarm`.

## Modifying the Bank Alarm Circuit

### Add more LEDs

Add four more LEDs and resistors, connecting them to pins 8, 7, 6 and 5.

Change the colours of the cables to make it easier to read. 

Each Ground wire should be black. 

Set the resistance for each resistor to 220 Ω.

![[loopAddLEDs.png]]

At the end of the process, your wiring diagram should be similar to this.

![[loopMultipleLEDs.png]]

## Adding functionality

To add additional functionality, you’ll be using loops to configure the LED pins as output and then be using other loops to access each LED.

Remove the `pinLED` constant and create an empty `for` loop in setup().

![[loopDefineLoop.png]]

```arduino
for (int pinLED = 5; pinLED <= 9; pinLED++) {
   
}
```

Move the line `pinMode(pinLED, OUTPUT);` to be inside the for loop block.

![[loopPinModeAllLEDs.png]]

```arduino
pinMode(pinLED, OUTPUT);
```

Update `setLEDBrightness()` to access the pins through a loop instead of writing to the individual pin. The `for` loop condition will be exactly the same as the one used in `setup()`.

![[loopAnalogWrite.png]]

```arduino
for (int pinLED = 5; pinLED <= 9; pinLED++) {
	analogWrite(pinLED, LEDBrightness);
  }
```

## Test the Functionality

Run the simulation and test to ensure that the functionality is as expected. 

<aside>
‼️ You may notice there’s an issue with two of the LEDs - It’s got to do with something called **Pulse Width Modulation**. Can you work out what the issue is?

</aside>

# Extension Exercises

1. Using a for loop, set pins 2 to 5 as OUTPUT pins. Do this in setup(). 
	1. Attach LEDs to pins 2 to 5 (inclusive). Update loop(), using a for loop, to turn each each LED on, wait a second, and then turn them off in another for loop.

[https://www.tinkercad.com/things/hyZxJA5vnY5](https://www.tinkercad.com/things/hyZxJA5vnY5)

1. In a new Circuit, attach a button to pin 2 and a LED to pin 10. Using a while loop, code the circuit to turn the LED on when the button is pressed, and off when the button is not pressed.

## Answers

This video shows how to approach and solve the first question, using For loops to access LEDs on different pins with efficient code.

![https://youtu.be/_TbOxZKevcw](https://youtu.be/_TbOxZKevcw)

# Review

1. What is the difference between the available types of loops? Why choose one of the other/s?
2. How many times can loops iterate?
3. Write the steps in plain language, **using loops**, to 
	1. Read in individual lines of a text file (use the one shown)
	2. Calculate the GST
	3. Output the GST component to the user.