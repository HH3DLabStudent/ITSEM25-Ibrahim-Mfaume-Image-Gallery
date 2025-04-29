# Image-Gallery
Rotary Encoder Image Viewer on TFT Display
==========================================

This project displays 16-bit color images on a TFT screen and allows users to cycle through them using a rotary encoder.

----------------------------
Features
----------------------------
- Displays RGB565 images on a TFT using the TFT_eSPI library
- Uses a rotary encoder to switch images
- Modular design for easily adding more images
- Basic debouncing for reliable input

----------------------------
Requirements
----------------------------
Hardware:
- ESP32 or similar microcontroller
- TFT Display (e.g., ILI9341 or ST7735)
- Rotary Encoder (CLK + DT pins)
- Optional pull-up resistors

Libraries:
- TFT_eSPI (https://github.com/Bodmer/TFT_eSPI)
- Arduino core for ESP32

----------------------------
Wiring
----------------------------
Component      | Microcontroller Pin
---------------|---------------------
Rotary CLK     | GPIO 17
Rotary DT      | GPIO 18
TFT Display    | Defined in TFT_eSPI User_Setup.h

Configure `User_Setup.h` in the TFT_eSPI library to match your display's wiring.

----------------------------
File Structure
----------------------------
project-folder/
├── main.ino       // Arduino sketch
├── image1.h       // 200x200 image in RGB565 format
├── image2.h       // Another image
└── README.txt     // This file

----------------------------
Image Storage Notes
----------------------------
- Images must be 200x200 in size
- Use RGB565 format stored as uint16_t arrays
- To save RAM, store image data in PROGMEM:
  const uint16_t image1[] PROGMEM = { ... };

- Read pixels with:
  pgm_read_word(&img[i]);

Tools for image conversion:
- LCD Image Converter: https://www.riuson.com/lcd-image-converter

----------------------------
Usage
----------------------------
1. Upload the sketch to your ESP32.
2. Rotate the encoder to cycle through images.
3. Images display on the TFT screen accordingly.

Enjoy!
