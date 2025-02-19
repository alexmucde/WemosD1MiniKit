[<< Zurück](README.md)

Hier die Lösung. Jedes mal wenn du drückst schaltest du die Taste ein und aus.

```
const int tasten_pin = D3;
const int led_pin = BUILTIN_LED;

int tasten_zustand = 0;
int letzter_tasten_zustand = 0;
int LED_zustand = 0;

// Diese Funktion initialisert den Mikrocontroller und das Programm
void setup() {

  pinMode(led_pin,OUTPUT);
  pinMode(tasten_pin,INPUT);

  digitalWrite(led_pin, tasten_zustand);

}

// Die folgende Funktion wird immer und immer wieder aufgerufen
void loop() {

  tasten_zustand = digitalRead(tasten_pin);
  
  if((letzter_tasten_zustand == LOW) && (tasten_zustand == HIGH))
  {
     if(LED_zustand == LOW)
       LED_zustand = HIGH;
     else if(LED_zustand == HIGH)
       LED_zustand = LOW;
  }

  digitalWrite(led_pin, LED_zustand);  // LED einschalten
  
  letzter_tasten_zustand = tasten_zustand;
}
```

[<< Zurück](README.md)