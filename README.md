# -automatic-road-reflector-light
This project automates road reflector lights using an Arduino and an LDR sensor. The lights turn ON during low light conditions (night) and OFF during the day, improving road safety while conserving energy. Simple to implement, low-cost, and easily scalable for real-world applications.
const int ldrPin = A0;
const int ledPin = 8;
int threshold = 500;

void setup() {
  pinMode(ledPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  int ldrValue = analogRead(ldrPin);
  Serial.println(ldrValue);

  if (ldrValue < threshold) {
    digitalWrite(ledPin, HIGH);
  } else {
    digitalWrite(ledPin, LOW);
  }

  delay(200);
}
