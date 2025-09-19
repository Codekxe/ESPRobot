# ESPRobot using the ESP32 DevKit DOIT V1 in conjunction with MIT App Inventor
Wiring: 
Left Motor -> A+, A-
Right Motor -> B+, B-

L293D:
IN1 -> 12
IN2 -> 13
IN3 -> 18
IN4 -> 19
VCC -> 3V3
GND -> GND
Published at https://gallery.appinventor.mit.edu/?galleryid=8fd19318-25fb-449e-9a06-6e6ae451fec8
Code: 
#include "BluetoothSerial.h"
BluetoothSerial BT;
#define IN1 12
#define IN2 13
#define IN3 18
#define IN4 19

void STOP() {
  analogWrite(IN1, 0);
  analogWrite(IN2, 0);

  analogWrite(IN3, 0);
  analogWrite(IN4, 0);
}

void UP() {
  analogWrite(IN1, 0);
  analogWrite(IN2, 255);

  analogWrite(IN3, 0);
  analogWrite(IN4, 255);
}

void DOWN() {
  analogWrite(IN1, 255);
  analogWrite(IN2, 0);

  analogWrite(IN3, 255);
  analogWrite(IN4, 0);
}

void LEFT() {
  analogWrite(IN1, 255);
  analogWrite(IN2, 0);

  analogWrite(IN3, 0);
  analogWrite(IN4, 0);
}

void RIGHT() {
  analogWrite(IN1, 0);
  analogWrite(IN2, 0);

  analogWrite(IN3, 255);
  analogWrite(IN4, 0);
}

void setup() {
  BT.begin("ESP32");
  pinMode(IN1, OUTPUT);
  pinMode(IN2, OUTPUT);
  pinMode(IN3, OUTPUT);
  pinMode(IN4, OUTPUT);
}

void loop() {
  if (BT.available()) {
    char read = BT.read();
    switch (read) {
      case "S":
        STOP();
        break;
      case "F":
        UP();
        break;
      case "B":
        DOWN();
        break;
      case "L":
        LEFT();
        break;
      case "R":
        RIGHT();
        break;
      default:
        break;
    }
  }
}
