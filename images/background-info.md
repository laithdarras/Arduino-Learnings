# Hardware Overview
![Parts](https://github.com/user-attachments/assets/a5bc375f-7fdd-4cbf-8027-d73f9526fcdb)
1. LED light source. Always an output.
2. Buzzer will emit a tone when OUTPUT is HIGH. Always an output.
3. OLED Display is a monochrome 128x64 pixels passive display matrix module with I2C Interface. This can be both an input or output device. It can be an output by emitting light when an electric current passes through. It can be an input by communicating with other devices (like the Arduino) using I2C protocol.
4. Button is a momentary push button. "Momentary" means that the button rebounds on its own after it is released. Always an input. Outputs a HIGH  signal when pressed, and LOW when released.
5. Potentiometers function as voltage dividers that can be used to both adjust voltage output to a circuit, and measure electric potential – hence the name potentiometer. This can be both an input or output device. It can be an output by adjusting the voltage output to a circuit. For example, adjusting the volume on a speaker. It can be an input by controlling inputs for electronic circuits. For example, controlling the brightness of a lamp by dimming the lights.
6. Light sensor uses a photo-resistor to detect light intensity. Always an input.
7. Sound sensor uses a microphone to detect sound intensity. Always an input.
8. A unique capacitive sensor element measures relative humidity and the temperature is measured by a negative temperature coefficient (NTC) thermistor. Always an input providing a digital output. Does NOT detect temps below freezing.
9. This measures temperature and atmospheric pressure. As the atmospheric pressure changes with altitude, it can also measure approximate altitude of a place. It can be connected to a microcontroller through I2C. Both an input or output device. Barometric pressure sensors detect atmospheric pressure changes as an input. Barometric pressure sensors convert the detected pressure changes into an electrical signal as an output.
10. The accelerometer contains three integrated circuits (ICs) that measure acceleration along each axis (x, y, z). The ICs monitor the capacitance of the fingers carved into the silicon, which changes when the fingers flex. The IC converts the capacitance change into a voltage, which is amplified and filtered by an op-amp circuit. This accelerometer can also monitor the surrounding temperature to tune the error caused by it. Both an input or output device. It can be an input by sensing elements that are oriented perpendicular to each other, measuring all vibration components affecting an object. The accelerometer outputs an electrical signal that is proportional to the input acceleration. The output voltage increases for positive accelerations and decreases for negative accelerations.

## Definitions:
- HIGH corresponds to 1, true, or logical high
- LOW corresponds to 0, false, or logical low
- I2C: Inter-Integrated Circuit protocol is a serial communication protocol that allows multiple devices to communicate with each other using two wires and unique addresses. 
![Introduction-to-I2C-Single-Master-Single-Slave](https://github.com/user-attachments/assets/c7347e3c-5caa-4219-ba4b-fda5028508b4)
- SDA (Serial Data) – The line for the master and slave to send and receive data.
- SCL (Serial Clock) – The line that carries the clock signal.
- Alternating Current (AC): The direction of the electrical current reverses back and forth at regular intervals.
- Direct Current (DC): The electrical current flows in one direction. DC is used in electronic devices because the components require a constant current to operate.

Read more on the I2C protocol with in-depth explanations of data transmission [here](https://www.circuitbasics.com/basics-of-the-i2c-communication-protocol/)

## Components
These are the default pins for each component on the Arduino board. You're able to use these, rather than the physical cables connecting to one another. The numbering is also labeled on top of each component on the physical board, so you don't have to reference this table all the time.


|   Modules      |   Interface   |   Pins/Address  |
| -------------- | ------------- | --------------- |
| LED            | Digital       | D4              |
| Buzzer         | Digital       | D5              |
| OLED Display   | I2C           | 0x78            |
| Button         | Digital       | D6              |
| Potentiometer  | Analog        | A0              |
| Light          | Analog        | A6              |
| Sound          | Analog        | A2              |
| Temp Sensor    | Digital       | D3              |
| Air Pressure   | I2C           | 0x77            |
| 3-Axis Accel.  | I2C           | 0x19            |


We now know what I2C is, but what the heck is the difference between Digital and Analog and how do we know which component carries out which interface?
- **Digital signal** refers to the value of the amplitude is discrete, limited to a number of finite values. Only has two states, LOW (0V) for 0; HIGH (5V) for 1.
- An **analog signal** is one that can take on any number of values, unlike a digital signal which has only two values: HIGH and LOW
![download](https://github.com/user-attachments/assets/e03a1366-ee98-4a42-af08-f743eae8f2a1)

Let's think of some real-world examples of analog and digital signals:
- Analog: Volume knob, thermometer, etc.
- Digital: Keyboard, cell-phone, tablet, etc.

## What is PWM?
Pulse Width Modulation, or PWM, is a technique for getting analog results with digital means. 

Digital control is used to create a square wave, a signal switched between on and off. This on-off pattern can simulate voltages in between full on (5 Volts) and off (0 Volts) by changing the portion of the time the signal spends on versus the time that the signal spends off. The duration of "on time" is called the pulse width. To get some analog values, you change, or "modulate", that pulse width. If you repeat this on-off pattern fast enough, the result is as if the signal is a steady voltage between 0 and 5V as a AC signal.

To generate PWM signals in Arduino, you can use analogWrite(), in contrast to using digitalWrite() to generate DC signals.

## What is the Serial Monitor?
Serial Monitor is a really nice tool to observe results on Arduino, it can be very useful in terms of printing results from the sensors or debugging in general. You can also send data back to the controller via the serial monitor to do certain tasks!


