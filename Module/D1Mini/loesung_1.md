[<< Zurück](README.md)

Hier die Lösung. Mit folgendem Programm blinkt die LED im Rythmus 500ms an und 1s aus.

```
// Diese Funktion initialisert den Mikrocontroller und das Programm
void setup()
{

   Serial.begin(9600);  // Intialisierung des seriellen Ports

}

// Die folgende Funktion wird immer und immer wieder aufgerufen
void loop() 
{

  Serial.print("Hello world\n");  // Schreibe "Max Mustermann" auf die serielle Konsole

  delay(2000);                    // Warte 2s
}
```

[<< Zurück](README.md)