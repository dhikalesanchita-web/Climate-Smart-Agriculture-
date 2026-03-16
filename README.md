# Climate-Smart-Agriculture-
Farming Based 
int rainSensor = 2;     // Rain sensor digital pin
int buzzer = 8;         // Buzzer pin
int led = 13;           // LED pin

void setup() {
  pinMode(rainSensor, INPUT);
  pinMode(buzzer, OUTPUT);
  pinMode(led, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  int rainState = digitalRead(rainSensor);

  if (rainState == LOW) {   // Rain detected
    Serial.println("Rain Detected");
    digitalWrite(buzzer, HIGH);
    digitalWrite(led, HIGH);
  } 
  else {                    // No rain
    Serial.println("No Rain");
    digitalWrite(buzzer, LOW);
    digitalWrite(led, LOW);
  }

  delay(1000);
}