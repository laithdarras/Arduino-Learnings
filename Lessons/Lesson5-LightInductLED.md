# Lesson 5: Making a Light Induct LED

The light sensor contains a photo-resistor to measure the intensity of light. The resistance of the resistor decreases with the increase of light intensity. The LED will light up if the surrounding is dark, and stays off if the surrounding is bright.

This will be a good lesson to utilize the Serial Monitor to observe results from our sensor.

Open the Serial Monitor in Tools -> Serial Monitor

The input will be the light sensor and our output will be the LED components.

This is the code:
```
// Light Switch
int sensorpin = A6; // Analog input pin that the sensor is attached to
int ledPin = 4;    // LED port
int sensorValue = 0;        // value read from the port
int outputValue = 0;        // value output to the PWM (analog out)

void setup() {
  pinMode(ledPin,OUTPUT);
  pinMode(sensorpin, INPUT);
  Serial.begin(9600);
}

void loop() {
  sensorValue = analogRead(sensorpin);

  Serial.println(sensorValue);

  if (sensorValue < 200) {
    digitalWrite(ledPin, HIGH);
  }
  else {
    digitalWrite(ledPin, LOW);
  }

  delay(200);
}
```

## Description:
The Serial.begin() method has one parameter:
- speed: speed of serial communication (ex// 9600, 115200, etc.)

Sets the data rate in bits per second (baud) for serial data transmission in the Serial monitor.

The software running on the computer communicates with the development board, and the baud rate is 9600.

The Serial.println() method has 1-2 parameters:
- val: value to print
- format: specifies the number base or the number of decimal places

This will print the data to the serial port as human-readable ASCII text followed by a carriage return character (ASCII 13, or '\r') and a newline character (ASCII 10, or '\n'). This command takes the same forms as Serial.print(). (ln means new line in the CLI)

The LED module will light up if it's dark and stay off if it's bright.
