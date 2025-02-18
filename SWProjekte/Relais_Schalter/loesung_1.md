[<< Zurück](README.md)

Hier die Lösung. Mit folgendem Programm kannst du das Relais mit der Taste abwechselnd ein- und ausschalten.

```
const int tasten_pin = D3;
const int led_pin = BUILTIN_LED;
const int relais_pin = D1;  // Initialisiere den Pin für das Relais

bool tasten_zustand = 0;
bool tasten_zustand_alt = 0;

bool relais_zustand = 0;

// Diese Funktion initialisert den Mikrocontroller und das Programm
void setup() {

  pinMode(led_pin,OUTPUT);
  pinMode(tasten_pin,INPUT);

  digitalWrite(led_pin, tasten_zustand);

  pinMode(relais_pin, OUTPUT);

}

// Die folgende Funktion wird immer und immer wieder aufgerufen
void loop() {

  tasten_zustand = digitalRead(tasten_pin);
  
  if(tasten_zustand_alt == HIGH && tasten_zustand == LOW)
  {
    if(relais_zustand == LOW)
    {
       digitalWrite(relais_pin, HIGH); // Relais ausschalten
       relais_zustand = HIGH;
    }
    else
    {
       digitalWrite(relais_pin, LOW); // Relais ausschalten
       relais_zustand = LOW;
    }
  }

  tasten_zustand_alt = tasten_zustand;

}
```

[<< Zurück](README.md)