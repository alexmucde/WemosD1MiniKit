[<< Zurück](../README.md)

# Micro SD

## Bilder

<img src="Bilder/vorne.JPEG" alt="drawing" width="200"/>

## Beschreibung

Das Modul hat einen Mirko SD Kartenleser.

- Pins: D8 (SS), D7 (MOSI), D6 (MISO), D5 (CLK), GND, 3V3

## Blockschaltbild

<img src="Bilder/pins.jpg" alt="drawing" width="300"/>

## Anwendung

Stecke das Mikro SD Modul auf einen der zwei freien Steckplätze. Achte auf die richtige Orientierung der Pins, RST auf RST und Tx auf Tx.

## Bibliothek

- SD von Arduino, SparkFun

## Beispielprogramm 1: Schreiben und Lesen einer Datei

Wir schreiben und Lesen eine Datei auf einer Mikro SD Karte.

Dazu schreiben wir folgendes Programm

```
/*
 * Micro SD Shield - Read/Write
 *
 * This example shows how to read and write data to and from an SD card file
 *
 * The WeMos Micro SD Shield uses:
 * D5, D6, D7, D8, 3V3 and G
 *
 * The shield uses SPI bus pins:
 * D5 = CLK
 * D6 = MISO
 * D7 = MOSI
 * D8 = CS
 *
 * The SD card library uses 8.3 format filenames and is case-insensitive.
 * eg. IMAGE.JPG is the same as image.jpg
 *
 * created Nov 2010 by David A. Mellis
 * modified 9 Apr 2012 by Tom Igoe
 *
 * This example code is in the public domain.
 * https://github.com/esp8266/Arduino/blob/master/libraries/SD/examples/ReadWrite/ReadWrite.ino
 */

#include <SPI.h>
#include <SD.h>

// change this to match your SD shield or module;
// WeMos Micro SD Shield V1.0.0: D8
// LOLIN Micro SD Shield V1.2.0: D4 (Default)
const int chipSelect = D8;

File myFile;

void setup()
{
  // Open serial communications and wait for port to open:
  Serial.begin(9600);
  while (!Serial) {
    ; // wait for serial port to connect. Needed for Leonardo only
  }

  Serial.print("Initializing SD card...");

  if (!SD.begin(chipSelect)) {
    Serial.println("initialization failed!");
    return;
  }
  Serial.println("initialization done.");

  // open the file. note that only one file can be open at a time,
  // so you have to close this one before opening another.
  myFile = SD.open("test.txt", FILE_WRITE);

  // if the file opened okay, write to it:
  if (myFile) {
    Serial.print("Writing to test.txt...");
    myFile.println("testing 1, 2, 3.");
    // close the file:
    myFile.close();
    Serial.println("done.");
  } else {
    // if the file didn't open, print an error:
    Serial.println("error opening test.txt");
  }

  // re-open the file for reading:
  myFile = SD.open("test.txt");
  if (myFile) {
    Serial.println("test.txt:");

    // read from the file until there's nothing else in it:
    while (myFile.available()) {
      Serial.write(myFile.read());
    }
    // close the file:
    myFile.close();
  } else {
    // if the file didn't open, print an error:
    Serial.println("error opening test.txt");
  }
}

void loop()
{
  // nothing happens after setup
}
```
Kompiliere und lade das Programm hoch, wie bereits in der Installation gelernt.

[<< Zurück](../README.md) 