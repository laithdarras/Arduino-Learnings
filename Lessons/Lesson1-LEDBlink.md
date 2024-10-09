The first thing we will do is make the LED on the arduino blink on its own repetitively. Make sure you're arduino is connected to your PC and you have the IDE opened up to write some C++ code. 

We want the LED to turn on for one second and then turn off for one second. This code does that, but what the heck does it mean?

```C++
int ledPin = 4;
void setup() {
    pinMode(ledPin, OUTPUT);
}
void loop() {
    digitalWrite(ledPin, HIGH);
    delay(1000);
    digitalWrite(ledPin, LOW);
    delay(1000);
}
```

Let's break it down step by step:
- setup() is the function called when the program starts. This will only run once in your program. Every single program you write will require a setup() function. You can use it initialize variables, pin modes, start using libraries, etc.
- loop() is the function called after the setup() has been called, and well... loops consecutively. Use this function to control the board.

```int ledPin = 4;``` This initializes the LED pin variable that we will use to call in our function to turn on/off. But why is it set to 4? This now takes us to a deeper level in understanding I/O and Digital vs Analog. Take a look at the **background-info.md** file in the **images** directory.

Now in the setup() function, we declared the pinMode(ledPin, OUTPUT) function. pinMode() has two parameters: **pin** and **mode**.
- pin: the Arduino pin number to set the mode of
- mode: INPUT, OUTPUT, or INPUT_PULLUP
    - Input: reads data from senser returning a binary value of HIGH or LOW
    - Output: Writes data to an actuator, such as an LED
    - Input pullup: Similat to input but also enables an internal pull-up resistor to keep the signal HIGH by default

 digitalWrite() function writes a HIGH or LOW value to a pin. It also has two parameters: pin (Arduino pin number) and value (HIGH or LOW).
 delay() function stops the program for a certain period of time, in this case it stops for 1 second (1000ms). It has one parameter which is just ms, the number of milliseconds to pause.
 
 


