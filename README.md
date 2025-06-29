# SuT_Task1

Task 1 - Week 2 (Summer Training)

## About This Task
A control task implementing a Gearmotor and 2 LEDs operated via push-button inputs.

* components used:
  
Arduino

BreadBoard

Hobby Gearmotor 

3v battery

2 LEDs

3 push-buttons

2 resistors 

jumper-wires
--------------------

## Hardware Configuration 

- using simulator

![Screenshot (517)](https://github.com/user-attachments/assets/d2c4ba4f-5af8-4b46-b333-acb604095b6b)







## Implementation

```
const int motorPin = 11;
const int LEDPin1 = 10;
const int LEDPin2 = 9;
const int butPin1 = 2;
const int butPin2 = 3;
const int butPin3 = 4;
int butState1;
int butState2;
int butState3;

void setup(){
  pinMode(motorPin, OUTPUT);
  pinMode(butPin1, INPUT_PULLUP); //pull up is an internal resistor (rather than using an external one), it sets the state of the button (off) by default
  pinMode(LEDPin1, OUTPUT);
  pinMode(butPin2, INPUT_PULLUP);
  pinMode(LEDPin2, OUTPUT);
  pinMode(butPin3, INPUT_PULLUP);
}

void loop(){
  butState1 = digitalRead(butPin1);
  butState2 = digitalRead(butPin2);
  butState3 = digitalRead(butPin3);
  
  if(butState1 == HIGH){
    digitalWrite(motorPin, LOW);
  }else{
    digitalWrite(motorPin, HIGH);
  }
  
  
    if(butState2 == HIGH){
    digitalWrite(LEDPin1, LOW);
  }else{
    digitalWrite(LEDPin1, HIGH);
  }
    if(butState3 == HIGH){
    digitalWrite(LEDPin2, LOW);
  }else{
    digitalWrite(LEDPin2, HIGH);
  }
}
```

