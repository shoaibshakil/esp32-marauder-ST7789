# esp32-marauder-ST7789
ESP32 Marauder firmware build for Kit hardware (ST7789 display + XPT2046 touch) documenting an open touch axis-swapping bug
# ESP32 Marauder Kit (v1.14.0) - ST7789 Display & Touch Axis Bug

This repository documents an active configuration build of **ESP32 Marauder (v1.14.0)** set up for custom kit hardware using an **ST7789 display** paired with an **XPT2046 touch controller** on an ESP32 Dev Module.

## Hardware Configuration
* **Microcontroller:** ESP32 Dev Module
* **Display Panel:** ST7789 TFT Display (Running in Landscape Mode)
* **Touch Controller:** XPT2046
* **Firmware Base:** ESP32 Marauder v1.14.0 (Latest Release)

## The Touch Issue Details
While the display initializes, clears the static noise, and renders the Marauder UI and selection menus correctly, the **touch input subsystem suffers from a severe axis-mapping and inversion bug**:

* **Cross-Mapped Axes:** The touch coordinates are completely out of sync with the visual landscape layout. For instance, horizontal inputs/touches trigger vertical navigation shifts, and vice versa. 
* **Failed Calibration:** Standard custom calibration arrays (`calData[5]`) and built-in `TFT_eSPI` landscape rotation flags inside `Display.cpp` fail to properly align the raw touch grid with the menu selection bars. 
* **Inaccurate Taps:** Tapping directly on a highlighted menu row doesn't register correctly; inputs feel shifted, rotated, or mirrored relative to where the finger lands on the screen.

## Help Wanted / Contributing
If you are experienced with `TFT_eSPI` touch mapping, XPT2046 driver tuning, or fixing coordinate matrices for ST7789 panels in ESP32 Marauder, contributions, suggestions, and pull requests to solve this touch layout bug are extremely welcome!
