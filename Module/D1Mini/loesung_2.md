[<< Zurück](README.md)

Hier die Lösung. Mit folgendem Programm gibst du deinen Namen jede Sekunde aus.

```
// Diese Funktion initialisert den Mikrocontroller und das Programm
void setup()
{

   Serial.begin(9600);  // Intialisierung des seriellen Ports

}

// Die folgende Funktion wird immer und immer wieder aufgerufen
void loop() 
{

  Serial.print("Max Mustermann\n");  // Schreibe "Max Mustermann" auf die serielle Konsole

  delay(1000);                       // Warte 1s
}
```

[<< Zurück](README.md)