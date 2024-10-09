# Lesson 2: Pressing Button to Light Up LED

First things first, rest in peace Uncle Phil. 

Hahah but seriously.. first and foremost, we need to know that the input of a button is a digital signal, and that there are only two states, 0 or 1. So we can control the output based on those two states. 

This lesson will require the button and the LED components. Both the sensor and the LED use digital signals, so they should be connected to digital interfaces.

This is the code:
```
//Button to turn ON/OFF LED
//Constants won't change. They're used here to set pin numbers:
const int buttonPin = 6;     // the number of the pushbutton pin
const int ledPin =  4;      // the number of the LED pin

// variables will change:
int buttonState = 0;         // variable for reading the pushbutton status

void setup() {
  pinMode(ledPin, OUTPUT);     // initialize the LED pin as an output:
  pinMode(buttonPin, INPUT);   // initialize the pushbutton pin as an input:
}

void loop() {
  buttonState = digitalRead(buttonPin);     // read the state of the pushbutton value:

  // check if the pushbutton is pressed. If it is, the buttonState is HIGH:
  if (buttonState == HIGH) {
    digitalWrite(ledPin, HIGH);   // turn LED on
  } else {
    digitalWrite(ledPin, LOW);   // turn LED off
  }
}
```
## Description
The same logic as lesson 1 goes for pinMode and the initialization of variables. Now in the loop() function, we have the if-statement:
- This statement is used to read the states of digital pins, either HIGH or LOW. When the button is pressed, the state is HIGH, otherwise is LOW.

The if…​else allows greater control over the flow of code than the basic if statement, by allowing multiple tests to be grouped. An else clause (if at all exists) will be executed if the condition in the if statement results in false. The else can proceed another if test, so that multiple, mutually exclusive tests can be run at the same time.

The usage of the statement is: if the logical expression in parentheses is true, execute the statement in curly braces after if, if not, execute the statement in curly braces after the else. If the state of the button is high, the LED pin outputs a high level and turn the LED on, else turn LED off.


