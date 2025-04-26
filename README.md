🍺 Alcohol Detection System

An alcohol detection system developed using Arduino Uno and MQ-3 sensor to enhance vehicle safety by preventing intoxicated driving.

🚀 Project Overview
- Objective: Detect alcohol presence in the driver’s breath and trigger a buzzer alert if alcohol is detected.
- Hardware Used: Arduino Uno, MQ-3 Alcohol Sensor, Buzzer, Breadboard, Resistors, LEDs.
- Programming Language: Embedded C (Arduino Sketch)
- Team: Collaborated with 2 other teammates.
  
🛠️ Features
- Real-time alcohol level detection.
- Immediate buzzer alert if alcohol level crosses a threshold.
- Serial Monitor output for alcohol levels.
- Hands-on experience with sensor calibration and microcontroller interfacing.

🔥 How it Works
1. The MQ-3 sensor continuously monitors the alcohol content.
2. If the alcohol level exceeds a pre-set threshold, the buzzer is triggered.
3. Otherwise, the system remains silent, ensuring normal vehicle operation.

📄 C Code 

const int mq3SensorPin = A0;
const int buzzerPin = 9;
const int alcoholThreshold = 300;

void setup() {
  Serial.begin(9600);
  pinMode(mq3SensorPin, INPUT);
  pinMode(buzzerPin, OUTPUT);
}

void loop() {
  int sensorValue = analogRead(mq3SensorPin);
  Serial.print("Alcohol Level: ");
  Serial.println(sensorValue);

  if (sensorValue > alcoholThreshold) {
    digitalWrite(buzzerPin, HIGH);
    Serial.println("Alcohol detected! Warning buzzer ON!");
  } else {
    digitalWrite(buzzerPin, LOW);
  }
  
  delay(500);
}
