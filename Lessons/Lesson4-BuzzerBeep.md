# Lesson 4: Make Buzzer Go BEEP

Finally, a break from the LED :D

But, just like the LED, the buzzer is an output module. Instead of the light, it produces a beep sound. 

The formal name for the buzzer is called the **Piezo Buzzer**. Is this an active or passive buzzer? And what is the difference between both?

Both are used to produce sounds, but function a bit differently and here's how:
- Active buzzers: Has an internal oscillation source that makes the buzzer sound whenever power is applied.
   - Active buzzers are used in computers, printers, alarms, electronic toys, car electronics, telephones, timers and other electronic product sounding devices.
- Passive buzzers: Has no internal source of oscillation and needs to be driven by a square wave and a different frequency. It acts like an electromagnetic speaker, and the changing input signal produces sound, rather than a tone automatically.
![buzzer-ap](https://github.com/user-attachments/assets/d434ba88-d7cf-4058-b852-89b7f2f1b894)

Now, the kit uses a passive buzzer so that it needs an AC signal to control. This then leads us to the next question, how to generate AC signals with Arduino! We use PWM! Learn what PWM and AC/DC power is in the images directory.

The code is here:
```
int BuzzerPin = 5;

void setup() {
  pinMode(BuzzerPin, OUTPUT);
}

void loop() {
  analogWrite(BuzzerPin, 128);
  delay(1000);
  analogWrite(BuzzerPin, 0);
  delay(0);
}
```

This writes an analog value (PWM wave) to a pin. After a call to analogWrite(), the pin will generate a steady rectangular wave of the specified duty cycle until the next call to analogWrite() on the same pin.

analogWrite() has two parameters, pin and value:
- pin: the Arduino pin to write to
- value: the duty cycle between 0 (always off) and 255 (always on).

The buzzer beeps.


Now that we have learned the use of PWM, in addition to using PWM to control the passive buzzer, we can also use PWM to control the speed of the motor and the brightness of the LED lights and etc.

As the diagram indicates below, use analogWrite() to generate PWM waves, the higher the percentage of Duty Cycle, the brighter the LED.
![PWM-LED](https://github.com/user-attachments/assets/5939e456-4239-4d20-9f5b-b08d43855041)

However, the LED Module on the Arduino cannot be directly controlled by PWM, because the LED module is connected to D4 and the PWM pins are 3, 5, 6, 9, 10, 11, and pin 4 is not a PWM pin. If you want to control the LED with PWM, you need to use the cable to connect to the port with PWM function.

Let's connect the LED to D3 using a cable:

Note: D3 is also inter-connected to the Temperature & Humidity Sensor, and therefore this example cannot be used together.

This is the code to be able to adjust the LED brightness using PWM signals:
```
int LED = 3;
int pot = A0;

void setup() {
  pinMode(LED, OUTPUT);
  pinMode(pot, INPUT);
}

void loop() {
  int potValue, value;
  potValue = analogRead(pot);
  value = map(potValue, 0, 1023, 0, 255); //Mapping potentiometer value to PWM signal value
  analogWrite(LED, value);
}
```

## Description:

The map() method has 5 parameters:
- value: the number to map
- fromLow: lower bound of the value's current range
- fromHigh: upper bound of the value's current range
- toLow: lower bound of the value's target range
- toHigh: upper bound of the value's target range

In our example, this maps the potentiometer sensor analog signal (0 to 1023) to the loudness of light (0 to 255).

This re-maps a number from one range to another. That is, a value of fromLow would get mapped to toLow, a value of fromHigh to toHigh, values in-between to values in-between, etc.

Note that the "lower bounds" of either range may be larger or smaller than the "upper bounds" so the map() function may be used to reverse a range of numbers, for example

y = map(x, 1, 50, 50, 1);

The function also handles negative numbers well, so that this example

y = map(x, 1, 50, 50, -100);

is also valid and works well!

The map() function uses integer math so will not generate fractions, when the math might indicate that it should do so. Fractional remainders are truncated and are not rounded or averaged.

Adjust the potentiometer to adjust the LED brightness.

All in all, when you want to use the PWM function, make sure to select those pins with a "~" symbol in front of their names.
