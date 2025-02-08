[<< Zurück](../README.md)

# Microcontroller D1 Mini

## Bild

TBD

## Ausstattung

- Microcontroller ESP-8266EX
- 4MB Flash
- Eingebaute LED am Pin 2
- SPI Bus
- I2C Bus
- Arbeitsspannung 3.3V
- 1 Analoger Eingang
- 11 Digitale EIngänge/Ausgänge

## Blockschaltbild

TBD

## Beispiel 1: Blinken der eingebauten LED

```
// Diese Funktion initialisert den Mikrocontroller und das Programm
void setup()
{

  pinMode(LED_BUILTIN, OUTPUT);  // Intialisierung der eingebauten LED am Pin 2

}

// Die folgende Funktion wird immer und immer wieder aufgerufen
void loop() 
{

  digitalWrite(LED_BUILTIN, LOW);   // Schalte die LED ein

  delay(1000);                      // Warte eine Sekunde

  digitalWrite(LED_BUILTIN, HIGH);  // Schalte die LED aus

  delay(2000);                      // Warte zwei Sekunden

}
```

## Beispiel 2: Serielle Ausgabe am Terminal

```
void setup()
{

}

void loop() 
{

}
```

[<< Zurück](../README.md)
