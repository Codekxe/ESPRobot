# ESPRobot using the ESP32 DevKit DOIT V1 in conjunction with MIT App Inventor
Wiring: 
Left Motor -> IN1, IN2
Right Motor -> IN3, IN4
Code: 
#define IN1 12
#define IN2 13
#define IN3 18
#define IN4 19
 
void setup()
{
  pinMode(IN1, OUTPUT);
  pinMode(IN2, OUTPUT);
  pinMode(IN3, OUTPUT);
  pinMode(IN4, OUTPUT);
}
 
void loop()
{
  // IN1 + IN2 : MOTOR1     IN3 + IN4 : MOTOR2
  // Call function control ROBOT HERE
}
 
void UP()
{
  analogWrite(IN1, 0);
  analogWrite(IN2, 255);  
 
  analogWrite(IN3, 0);
  analogWrite(IN4, 255);
}
 
void DOWN()
{
  analogWrite(IN1, 255);
  analogWrite(IN2, 0);  
 
  analogWrite(IN3, 255);
  analogWrite(IN4, 0);
}
 
void LEFT()
{
  analogWrite(IN1, 255);
  analogWrite(IN2, 0);  
 
  analogWrite(IN3, 0);
  analogWrite(IN4, 0);
}
 
void RIGHT()
{
  analogWrite(IN1, 0);
  analogWrite(IN2, 0);  
 
  analogWrite(IN3, 255);
  analogWrite(IN4, 0);
}
