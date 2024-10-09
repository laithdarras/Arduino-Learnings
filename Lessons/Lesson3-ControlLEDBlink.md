# Lesson 3: Controlling the Frequency of the Blink

Now, instead of the LED having only two states (on or off), wouldn't it be cool if we could adjust the rate at which the LED blinks? This is where the **potentiometer** comes in and the idea of **analog signals**!

Components needed will be the potentiometer (input) and LED (output). The input is an analog signal, so it is connected to the analog signal interface, the LED module is connected to the digital signal interface. 

This is the code:
```
int potPin = A0;    // select the input pin for the potentiometer
int ledPin = 4;      // select the pin for the LED
int potValue = 0;  // variable to store the value coming from the potentiometer

void setup() {
  pinMode(ledPin, OUTPUT);
  pinMode(potPin, INPUT);
}

void loop() {
  potValue = analogRead(potPin);     // read the value from the sensor
  digitalWrite(ledPin, HIGH);
  delay(potValue);
  digitalWrite(ledPin, LOW);
  delay(potValue);
}
```

## Description:
You may find that we defined rotaryPin and ledPin in different ways. This is because Potentiometer generates an analog signal, and the LED is controlled by a digital signal.
- To define for Analog Pin, use A + the number of the Pin (For Example here A0).
- To define for Digital Pin, use just the number of the pin (For Example here 4).

We're also introduced to a new function, analogRead(). One parameter, pin.
- pin: the name of the analog input to read from
    - Returns: The analog reading on the pin. Although it is limited to the resolution of the analog to digital converter (0-1023 for 10 bits or 0-4095 for 12 bits). Arduino boards contain a multichannel, 10-bit analog to digital converter.

 We specify the delay() function with potValue because the value is the value of the analog signal of the knob pin being read, so the delay time can be controlled by the knob.

 Once done correctly, turning the Potentiometer will change the frequency of LED flickering.
