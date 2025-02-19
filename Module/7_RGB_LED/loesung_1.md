[<< Zurück](README.md)

Hier die Lösung. Mit folgendem Programm kannst du die äußeren LEDs in rot kreisen lassen.

```
// Verwendete Bibliotheken
#include <Adafruit_NeoPixel.h>

#define PIN           D2
#define ANZAHL_PIXEL  7

int zaehler = 1;

Adafruit_NeoPixel pixels(ANZAHL_PIXEL, PIN, NEO_GRB + NEO_KHZ800);

// Diese Funktion initialisert den Mikrocontroller und das Programm
void setup()
{

  pixels.begin();  // Intialisierung der NeoPixel Bibliothek

}

// Die folgende Funktion wird immer und immer wieder aufgerufen
void loop() 
{
  pixels.clear();   // Alle Pixel zurücksetzen
  int num;
  for(num=0;num<7;num++)
  {
    if(num==zaehler)
      pixels.setPixelColor(num, pixels.Color(255, 0, 0));   // Setze die drei Farben Rot, Grün, Blau
    else
      pixels.setPixelColor(num, pixels.Color(0, 0, 0));   // Setze die drei Farben Rot, Grün, Blau
  }
  pixels.show();    // Sende die neue Farbe an die LED

  delay(100);      // Warte eine Sekunde

  zaehler++;

  if(zaehler==7)
    zaehler=1;
}
```

[<< Zurück](README.md)