[<< Zurück](README.md)

Hier die Lösung. Mit folgendem Programm kannst du die LED abwechselnd ein und ausschalten bei jeder Bewegung.
Achte darauf dass du die Hand nicht zu schnell bewegst.

```
const int pin = D3;
int PIR_zustand = LOW;
int letzter_PIR_zustand = LOW;
int LED_zustand = HIGH;

// Diese Funktion initialisert den Mikrocontroller und das Programm
void setup()
{

  pinMode(pin, INPUT);
  pinMode(BUILTIN_LED, OUTPUT);

  digitalWrite(BUILTIN_LED, LED_zustand); // Schalte LED aus

}

// Die folgende Funktion wird immer und immer wieder aufgerufen
void loop()
{

  PIR_zustand = digitalRead(pin);   // Lese des Status des PIR

  if((letzter_PIR_zustand == LOW) && (PIR_zustand == HIGH))
  {
     if(LED_zustand == LOW)
       LED_zustand = HIGH;
     else if(LED_zustand == HIGH)
       LED_zustand = LOW;
  }
    
  digitalWrite(BUILTIN_LED, LED_zustand); // Schalte LED aus
  
  letzter_PIR_zustand = PIR_zustand;
}
```

[<< Zurück](README.md)