# MicroFoundry-ESP32-C3-Breakout-PCB-v5.0
The Micro Foundry ESP32-C3 MCU Breakout PCB is a small form-factor PCB (26x26mm) was initially designed to provide the processing and network connectivity for the Micro Foundry line of ToF (Time of Flight) sensor breakout PCBs.

## Description
The breakout is based on Espressif's ESP32-C3 family of cost-effective RISC-V MCU with Wi-Fi and Bluetooth 5 (LE) connectivity for secure IoT applications. An official ESP32-C3 module provides single-core ESP32-C3 chip with a maximum clock speed of 160MHz, 4MB of Flash, 400KB of SRAM and up to 15 GPIO. Additional details can be found on Espressif's [ESP32-C3 product page](https://www.espressif.com/en/products/socs/esp32-c3). The breakout includes an ST LD39050 3.3v 500mA low noise LDO, a 10 position FFC connector for sensor connectivity, a JST SH compatible 6 position connector for power and external IO access, a 4 position JST SH [Adafruit STEMMA QT](https://learn.adafruit.com/introducing-adafruit-stemma-qt) / [SparkFun Qwiic](https://www.sparkfun.com/qwiic) I2C compatible connector for accessories, and the required passives and LED indicators.

Runs [Arduino with Espressif's ESP32 core](https://github.com/espressif/arduino-esp32) and you can also run [MicroPython](https://micropython.org/download/esp32c3-usb/) on this chipset.

## Details
- ESP32-C3 32-bit RISC-V single core processor with 4MB of Flash memory, 400 KB of SRAM
- Available with either PCB patch antenna or w.FL / MHF3 / IPX3 external atenna connector
- 6 position JST SH style connector for 5v input, LDO Enable IO and 3 additional ESP32-C3 IO
- 10 position 1.0mm pitch FFC connector providing 3.3v regulated power, I2C and 6 additional IO
- 4 position JST SH style connector for STEMMA QT /Qwiic port for plug and play I2C connections
- 8 position contact pads for a custom Micro Foundry progamming adapter
- LED indicators for 5v source power (Red), 3v3 power (Green) and ESP32-C3 User LED (Blue)
- Provisions for an optional Infineon SLS32AIA010MH USON10 [OPTIGA Trust-M](https://www.infineon.com/cms/en/product/security-smart-card-solutions/optiga-embedded-security-solutions/optiga-trust/optiga-trust-m-express/) cryptographic security IC

## Pinouts
### Power/IO
JST SH style connector, 1.0mm Pitch, 6 Position

| Pin | Function | Description | ESP32-C3 IO |
| --- | -------- | ----------- | ---------- |
| 1 | GND | Ground | |
| 2 | Vin | Voltage In 3.5 to 5.5vdc | |
| 3 | EN | ESP32-C3 Enable | EN (Pull LOW to reset) |
| 4 | PS-EN | LDO39050 Enable | Input (Active HIGH) |
| 5 | PD-EN | Presence Detection Enable | IO5 as Input (Active HIGH) |
| 6 | PD-Out |Presence Detected | IO4 as Output (Active HIGH) |

### FFC Expansion Connector
10 position 1.0mm pitch FFC connector providing 3.3v regulated power, I2C and 6 additional IO

| Pin | Function | Description | ESP32-C3 IO |
| --- | -------- | ----------- | ---------- |
| 1 | 3v3 | Sensor Power | |
| 2 | GND | Ground | |
| 3 | SDA | I2C Data | IO2 |
| 4 | SCL | I2C Clock | IO3 |
| 5 | VL53-PWR | High Side Power Switch (on VL53 breakout) | IO7 as Output (Active HIGH) |
| 6 | VL53-Int | VL53L5 Interrupt | IO9 as Input (Active LOW) |
| 7 | VL53-I2C-RST | VL53L5 I2C Reset | IO6 as Output (Active HIGH) |
| 8 | VL53-LPn | VL53L5 Low Power Enable | IO8 as Output (Active LOW) |
| 9 | PD-LED1 | NO Presence Detection Indicator | IO0 as Output (Active HIGH) |
| 10 | PD-LED2 | Presence Detected Indicator | IO10 as Output (Active HIGH) |

### STEMMA QT / Qwiic
JST SH style connector, 1.0mm Pitch, 4 Position

| Pin | Function | Description | ESP32-C3 IO |
| --- | -------- | ----------- | ---------- |
| 1 | GND | Ground | |
| 2 | 3v3 | Voltage Out | |
| 3 | SDA | I2C Data | IO2 |
| 4 | SCL | I2C Clock | IO3 |

### Program/Debug Contact Pads
[Kyocera AVX 009258008004064](http://datasheet.octopart.com/009258008004064-KYOCERA-AVX-datasheet-165279551.pdf), 1.0mm Pitch 8 Position single piece connector

| Pin | Function | Description | ESP32-C3 IO |
| --- | -------- | ----------- | ---------- |
| 1 | GND | Ground | |
| 2 | 5v | Power | |
| 3 | EN | ESP32-C3 Enable | EN |
| 4 | Boot | ESP32-C3 Bootloader | IO9 |
| 5 | RXDO | High Side Power Switch (on VL53 breakout) | IO7 as Output (Active HIGH) |
| 6 | TXDO | VL53L5 Interrupt | IO9 as Input (Active LOW) |
| 7 | PS-EN | LDO39050 Enable | Input (Active HIGH) |
| 8 | PD-EN | Presence Detection Enable | IO5 as Input (Active HIGH) |

### ESP32-C3 Pins Not Exposed

| Pin | Function | Description | ESP32-C3 IO |
| --- | -------- | ----------- | ---------- |
| 1 | LED | ESP32-C2 Blue User Indicator | IO19 (Active LOW) |
| 2 | SEC_EN | OPTIGA Trust-M Enable | IO1 (Active HIGH) |

