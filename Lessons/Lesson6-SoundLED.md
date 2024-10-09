# Lesson 6: Sound Sensitive LED Light

The LED lights light up when the sound is made. When there is no sound and it is very quiet, the LED lights go off. The sound sensor can detect the sound intensity of the environment, and its output is also simulated. We will be using the Serial plotter to visualize the results.

Open Serial Plotter from Tools -> Serial Plotter

The code is here:
```
//Sound Control Light
int soundPin = A2; // Analog sound sensor is to be attached to analog
int ledPin = 4; // Digital LED is to be attached to digital
void setup() {
  pinMode(ledPin, OUTPUT);
  pinMode(soundPin, INPUT);
  Serial.begin(9600);
}
void loop(){
  int soundState = analogRead(soundPin); // Read sound sensor’s value
  Serial.println(soundState);

  // if the sound sensor’s value is greater than 400, the light will be on.
  //Otherwise, the light will be turned off
  if (soundState > 400) {
    digitalWrite(ledPin, HIGH);
    delay(100);
  }else{
    digitalWrite(ledPin, LOW);
  }
}
```
Serial port print the sound sensor’s value. So you open the serial monitor on the IDE interface, and you see the value of the output sensor.

The LED module will light up if the surrounding is loud enough.
