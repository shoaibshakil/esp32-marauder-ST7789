# ESP32 Marauder - ST7789 & XPT2046 Custom Build

A fully configured and working build of ESP32 Marauder (v1.14.3) optimized specifically for custom hardware setups... optimized specifically for custom hardware setups utilizing an **ST7789 TFT Display (240x320)** paired with an **XPT2046 Touch Controller** on an ESP32 Dev Module.

---

## 🚀 Features & Fixes Included
* **Display Integration:** Configured via `MARAUDER_V6` and `TFT_DIY` profiles for seamless ST7789 landscape rendering.
* **Color Correction:** Set `TFT_INVERSION_OFF` to ensure proper black backgrounds and standard color rendering.
* **Calibrated Touch:** Fixed axis inversion and coordinate-swapping bugs for the XPT2046 touch panel in landscape orientation.
* **Enhanced UI Navigation:** Integrated direct button mapping and touch handling for smooth menu navigation.
* **Modern Core Support:** Cleaned up linker errors and header duplicate definitions to compile cleanly on modern ESP32 Board Cores (v2.0.17).

---

## 📌 Hardware Pinout Configuration (`User_Setup.h`)
| Pin Function | ESP32 GPIO Pin |
| :--- | :--- |
| **TFT_MISO** | GPIO 19 |
| **TFT_MOSI** | GPIO 23 |
| **TFT_SCLK** | GPIO 18 |
| **TFT_CS** | GPIO 17 |
| **TFT_DC** | GPIO 16 |
| **TFT_RST** | GPIO 5 |
| **TFT_BL** | GPIO 32 |
| **TOUCH_CS** | GPIO 21 |
| **SD_CS** | GPIO 4 |

---

## 📦 Flashing Guide
Pre-compiled binaries are available in the **Releases** section. If you are flashing manually via `esptool` or a web flasher, use the following memory offsets:

* **Bootloader (`bootloader.bin`):** `0x1000`
* **Partitions (`partitions.bin`):** `0x8000`
* **Boot App (`boot_app0.bin`):** `0xE000`
* **Firmware (`esp32_marauder.ino.bin`):** `0x10000`
