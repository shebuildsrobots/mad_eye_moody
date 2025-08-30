# Build a Mad Eye Moody Eye 
This is a fork of the excellent thelastoutpostworkshop/ESP32LCDRound240x240Eyes repo. It includes some additional wiring instructions for Adafruit TFT boards plus 3D print files for an eye patch mount.

Materials:
*  [Adafruit 1.28" 240x240 Round TFT LCD Display with MicroSD - GC9A01A](https://www.adafruit.com/product/6178?srsltid=AfmBOorBGrz_fWfnvQ6gThZ-MIQiUJGEcYirGgny69Nzteqpp4ODeEO5). The tutorial linked in original repo uses a generic, non-Adafruit board. If using one of these boards, your code may vary from the instructions here.
*  ESP32.
*  Foam, leather, or material for head strap.
*  Portable battery pack. 

## Install and configure the TFT_eSPI library

You'll first need to download the [TFT_eSPI library](https://github.com/Bodmer/TFT_eSPI). 

In this library's directory, you'll find a file called User_Setup.h. If you're using the Adafruit board I linked, you must find and uncomment the following line:

`#define GC9A01_DRIVER`

Then, you must find and uncomment the lines corresponding to your ESP board. For me, this was:

```
// For ESP32 Dev board (only tested with GC9A01 display)
// The hardware SPI can be mapped to any pins
#define TFT_MOSI 19 // In some display driver board, it might be written as "SDA" and so on.
#define TFT_SCLK 18
#define TFT_CS   5  // Chip select control pin
#define TFT_DC   22  // Data Command control pin
#define TFT_RST  23  // Reset pin (could connect to Arduino RESET pin)
#define TFT_BL   4  // LED back-light

#define TOUCH_CS 21     // Chip select pin (T_CS) of touch screen
```

Save and close this file. Upload the code in this repo to your ESP32 and wire according to the pin mapping you just uncommented above. 

## Print the enclosure
I printed the base and top plate in PLA, glued a EVA foam strap to the sides, and then used M2 screws to sandwich the screen between the top plate and the base plate. Run the wires along the open side of the enclosure, along the side of your head, and behind the collar of your shirt. Use a portable battery to power the ESP32.  
