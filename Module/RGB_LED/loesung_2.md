[<< Zurück](README.md)

Hier die Lösung. Mit folgendem Programm lassen wir die LED wie eine Ampel blinken.

```
// Verwendete Bibliotheken
#include <Adafruit_NeoPixel.h>

#define PIN           D2
#define ANZAHL_PIXEL  1

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
  pixels.setPixelColor(0, pixels.Color(255, 0, 0));   // Setze die drei Farben Rot, Grün, Blau
  pixels.show();    // Sende die neue Farbe an die LED

  delay(5000);      // Warte eine Sekunde

  pixels.clear();   // Alle Pixel zurücksetzen
  pixels.setPixelColor(0, pixels.Color(255, 255, 0));   // Setze die drei Farben Rot, Grün, Blau
  pixels.show();    // Sende die neue Farbe an die LED

  delay(1000);      // Warte eine Sekunde

  pixels.clear();   // Alle Pixel zurücksetzen
  pixels.setPixelColor(0, pixels.Color(0, 255, 0));   // Setze die drei Farben Rot, Grün, Blau
  pixels.show();    // Sende die neue Farbe an die LED

  delay(5000);      // Warte zwei Sekunden

  pixels.clear();   // Alle Pixel zurücksetzen
  pixels.setPixelColor(0, pixels.Color(255, 255, 0));   // Setze die drei Farben Rot, Grün, Blau
  pixels.show();    // Sende die neue Farbe an die LED

  delay(2000);      // Warte zwei Sekunden
}
```

[<< Zurück](README.md)