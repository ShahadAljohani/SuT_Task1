# SuT_Task1

Task 1 - Week 2 (Summer Training)

## About This Task
A control task implementing a Gearmotor and 2 LEDs operated via push-button inputs.

* components used:
  
      Arduino

      BreadBoard

      Hobby Gearmotor 

      NMOS transistor

      3v battery

      2 LEDs

      3 push-buttons

      2 resistors 

      jumper-wires

----------------------------
### Breif Explanation of NMOS
N-channel MOSFET 	

NMOS - a transistor that has 3 pins. Gate, Drain, Source.

The gate is going to be connected to the Arduino to accept the low current from Arduino, because it only needs a voltage signal, not continuous current, and the current draw is minimal (just a short pulse while switching)

Power from the battery will flow out of the positive terminal of the battery, into the power bus (+ column in the BB) through the motor, then to the motor's negative terminal through the transistor, and then through the jumper wire to ground. Then, through the common ground to the battery (it is necessary) without short circuiting the positive voltages to each other (means not directly connecting 2 or more separate voltage sources, because they might have different voltage levels, which can cause damage)

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

