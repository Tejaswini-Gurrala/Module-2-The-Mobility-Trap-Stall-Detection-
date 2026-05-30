>Module 2: The Mobility Trap (Stall Detection)

>Objective:
 The objective of this module is to simulate motor stall detection using a pushbutton and an LED. The LED indicates    whether a stall condition has been detected or not.

>Components used :
 1. Arduino Uno
 2. Push Button
 3. 220 Ohm Resistor
 4. 10K Ohm Resistor
 5. Breadboard
 6. Jumper Wires

 >Mars Engineering Brief :
  To detect a motor stall, the rover can use current sensors to monitor how much current the motor is drawing. When a   wheel gets stuck in the Martian Sand, the motor has to work harder and starts drawing more current than before. 
  If the current becomes too high, the rover can identify it as a stall condition and immediately stop the motor.       This prevents overheating and protects the motor driver from damage. Using this method helps the rover continue       operating safely even when travelling through difficult terrain.

>Code file (in C) : [Module 2 _The_Mobility_Trap.c](https://github.com/user-attachments/files/28422086/Module.2._The_Mobility_Trap.c)

>Code explanation :
 I used INPUT_PULLUP for the pushbutton, so the button normally reads HIGH when it is not pressed. When the button is  pressed, the input becomes LOW. The program keeps checking the button state using an if-else statement. If the        button is pressed, the LED turns ON indicating that a stall has been detected. If the button is not pressed, the LED  remains OFF, indicating that no stall has been detected.

>Tinkercad Simulation Link : https://www.tinkercad.com/things/g3P7uWzHfWG-module-2/editel?returnTo=https%3A%2F%2Fwww.tinkercad.com%2Fdashboard&sharecode=LI8ZuOb_W_CSrWYZdLfNBtCsjpSzzESOhh_ei-azKtQ

>Code in text :
// C
// Defining pins
int led = 9;
int pushButton = 10;

void setup(){
  pinMode(pushButton, INPUT_PULLUP);
  /*Because of INPUT_PULLUP function, the push button voltage
  is HIGH initially, when we press the push button 
  it's voltage becomes LOW and LED turns ON as directed*/
  
  pinMode(led, OUTPUT);
}

void loop(){
  
  if(digitalRead(pushButton) == LOW){
     digitalWrite(led, HIGH);
  }
  
  else{
     digitalWrite(led, LOW);
  }
}



