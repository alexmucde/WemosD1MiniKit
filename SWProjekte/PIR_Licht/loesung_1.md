[<< Zurück](README.md)

Hier die Lösung. Mit folgendem Programm kannst du bei Bewegung die LED in Blau für 10s einschalten.
Achte darauf dass du die Hand nicht zu schnell bewegst.

```
// Verwendete Bibliotheken
#include <Adafruit_NeoPixel.h>

#define PIN_LED       D2
#define ANZAHL_PIXEL  1

Adafruit_NeoPixel pixels(ANZAHL_PIXEL, PIN_LED, NEO_GRB + NEO_KHZ800);

const int pin_led = D3;
int PIR_zustand = 0;
int PIR_zustand_alt = 0;
int zeit_zaehler = 0;

// Diese Funktion initialisert den Mikrocontroller und das Programm
void setup()
{

  pinMode(pin_led, INPUT);
  pinMode(BUILTIN_LED, OUTPUT);

  digitalWrite(BUILTIN_LED, HIGH); // Schalte LED aus

  pixels.begin();  // Intialisierung der NeoPixel Bibliothek

}

// Die folgende Funktion wird immer und immer wieder aufgerufen
void loop()
{

  PIR_zustand = digitalRead(pin_led);   // Lese des Status des PIR

  if (PIR_zustand_alt == LOW && PIR_zustand == HIGH)
  {
    pixels.clear();   // Alle Pixel zurücksetzen
    pixels.setPixelColor(0, pixels.Color(0, 255, 0));   // Setze die drei Farben Rot, Grün, Blau
    pixels.show();    // Sende die neue Farbe an die LED
    zeit_zaehler = 1;
  }

  if(zeit_zaehler==1000000)
  {
    pixels.clear();   // Alle Pixel zurücksetzen
    pixels.setPixelColor(0, pixels.Color(0, 0, 0));   // Setze die drei Farben Rot, Grün, Blau
    pixels.show();    // Sende die neue Farbe an die LED
    zeit_zaehler = 0;  
  }

  if(PIR_zustand == HIGH)
    zeit_zaehler = 1;
  else if(zeit_zaehler!=0)
    zeit_zaehler += 1;

  PIR_zustand_alt = PIR_zustand;
    
}
```

[<< Zurück](README.md)