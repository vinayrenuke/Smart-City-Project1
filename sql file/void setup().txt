void setup()
{
  Serial.begin(115200);
  pinMode(Button1, INPUT_PULLUP);
  pinMode(Button2, INPUT_PULLUP);
  pinMode(Button3, INPUT_PULLUP);
  pinMode(Moto1L, OUTPUT);
  pinMode(Moto1R, OUTPUT);
  pinMode(Moto2L, OUTPUT);
  pinMode(Moto2R, OUTPUT);

  digitalWrite(Moto1L, HIGH);
  digitalWrite(Moto1R, HIGH);
  digitalWrite(Moto2L, HIGH);
  digitalWrite(Moto2R, HIGH);
  delay(1000);
}

void loop()
{
  if (digitalRead(Button1) == 0)
  {
    delay(50);
    while (digitalRead(Button1) == 0)
    {    
      Serial.println("Button1 Pressed");
      digitalWrite(Moto1L, LOW);
      digitalWrite(Moto1R, HIGH);
      delay(100);
      digitalWrite(Moto1L, HIGH);
      digitalWrite(Moto1R, HIGH);
      delay(100);
    }
    digitalWrite(Moto1L, HIGH);
    digitalWrite(Moto1R, HIGH);
  }
  else if (digitalRead(Button2) == 0)
  {
    delay(50);
    while (digitalRead(Button2) == 0)
    {
      Serial.println("Button2 Pressed");
      digitalWrite(Moto1L, HIGH);
      digitalWrite(Moto1R, LOW);
      delay(100);
      digitalWrite(Moto1L, HIGH);
      digitalWrite(Moto1R, HIGH);
      delay(100);
    }
    digitalWrite(Moto1L, HIGH);
    digitalWrite(Moto1R, HIGH);
  }
  else if (digitalRead(Button3) == 0)
  {
    delay(150);
    while (digitalRead(Button3) == 0);
    Serial.println("Button3 Pressed");

    digitalWrite(Moto2L, LOW);
    digitalWrite(Moto2R, HIGH);
    delay(3000);
    digitalWrite(Moto2L, HIGH);
    digitalWrite(Moto2R, HIGH);
    delay(300);
    digitalWrite(Moto2L, HIGH);
    digitalWrite(Moto2R, LOW);
    delay(3000);
    digitalWrite(Moto2L, HIGH);
    digitalWrite(Moto2R, HIGH);
  }
}