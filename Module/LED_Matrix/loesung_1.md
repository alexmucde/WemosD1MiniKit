[<< Zurück](README.md)

Hier die Lösung. Mit folgendem Programm kannst du einen Ball von links nach rechts und wieder zurück bewegen lassen.

```
// Verwendete Bibliotheken
#include <Adafruit_GFX.h>
#include <WEMOS_Matrix_GFX.h>

MLED matrix(7); // Helligkeit=7 (Maximum)

int x = 0;
int richtung = 1;

// Diese Funktion initialisert den Mikrocontroller und das Programm
void setup() 
{
   
}

// Die folgende Funktion wird immer und immer wieder aufgerufen
void loop()
{
 
  matrix.clear(); // Bild löschen
  matrix.drawRect(x,3, 2,2, LED_ON);
  matrix.writeDisplay(); // Sende das neue Bild
  delay(500);
  
  x = x + richtung;

  if(x>6)
  {
    x = 5;
    richtung=-1;
  }  

  if(x<0)
  {
    x = 1;
    richtung=1;
  }  

}
```

[<< Zurück](README.md)