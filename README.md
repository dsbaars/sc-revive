# SC Revive

Software for an 256x128 RGB matrix panel, driven by an ESP32.

Can be used on devices which are were sold as "StockClock" by Stefan Stojchevski, unfortunately both the website and the author seem to have disappeared.

## Hardware

The hardware consists of:
- ESP32 Dev Kit
- 256x128 RGB Matrix (P4-256x128-2121-A5)

Connected with a HUB75 connector.

The StockClock hardware has the following pin-mapping:

| HUB75 Pin | ESP32 Pin | Arduino Pin Number |
| ---| ---- | --- |
| R1 | D25 |  25 |
| G1 | D26| 26|
| B1 | D27 | 27 |
| R2 | D21 | 21 |
| G2 | D22 | 22 |
| B2 | D23| 23 |
| A | D12 | 12 |
| B | RX1 | 16 |
| C | TX1 | 17 |
| D | D18 | 18 |
| LAT | D32 | 32|
| OE | D33 | 33 |
| CLK | D15 | 15 |

## Libraries 

### Adafruit Protomatter

````cpp
uint8_t rgbPins[] = {25, 26, 27, 21, 22, 23};
uint8_t addrPins[] = {12, 16, 17, 18};
uint8_t clockPin = 15; 
uint8_t latchPin = 32;
uint8_t oePin = 33;

````

### ESP32-HUB75-MatrixPanel-I2S-DMA

````cpp
#define R1_PIN 25 //D25
#define G1_PIN 26 //D26
#define B1_PIN 27 //D27
#define R2_PIN 21 //D21
#define G2_PIN 22 // D22
#define B2_PIN 23 //D23
#define A_PIN 12 //D12
#define B_PIN 16 // RX1
#define C_PIN 17 //TX1
#define D_PIN 18 //D18
#define E_PIN -1 // not used
#define LAT_PIN 32 //D32
#define OE_PIN 33 //D33
#define CLK_PIN 15 // D15
````

## Development

The following `platformio.ini` works

````ini
[env:esp32dev]
platform = espressif32
board = esp32dev
framework = arduino
````