[<< Zurück](README.md)

Hier die Lösung. Mit folgendem Programm kannst du das Relais 3s einschalten und 1/2s ausschalten.

```
const int relais_pin = D1;

// Diese Funktion initialisert den Mikrocontroller und das Programm
void setup()
{
  pinMode(relais_pin, OUTPUT);   // Initialisiere den Pin für das Relais
}

// Die folgende Funktion wird immer und immer wieder aufgerufen
void loop() 
{
  digitalWrite(relais_pin, HIGH); // Relais einschalten
  delay(3000);                  // Warte 2s
 
  digitalWrite(relais_pin, LOW);  // Relais ausschalten
  delay(500);                  // Warte 2s
}
```

[<< Zurück](README.md)