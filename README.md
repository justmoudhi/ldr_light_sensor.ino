# ldr_light_sensor.ino
const int LDR = A0;
const int LED = 8;
const int BUZZER = 9;

void setup() {
  pinMode(LED, OUTPUT);
  pinMode(BUZZER, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  int lightValue = analogRead(LDR);

  Serial.println(lightValue);

  if (lightValue < 400) {  // ظلام
    digitalWrite(LED, HIGH);
    digitalWrite(BUZZER, HIGH);
  } 
  else {                    // نور
    digitalWrite(LED, LOW);
    digitalWrite(BUZZER, LOW);
  }

  delay(100);
}