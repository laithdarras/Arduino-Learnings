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
