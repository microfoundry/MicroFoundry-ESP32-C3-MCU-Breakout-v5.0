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

| Pin | ESP32-C3 IO | Function | Description | Pin Settings Requirements |
| --- | ----------- | -------- | ----------- | -------------------------- |
| 1 |     | GND | Ground | |
| 2 |     | Vin | Voltage In 3.5 to 5.5vdc | |
| 3 | EN  | ESP32-C3 Enable | Run / Reset | Pull LOW to reset, pull-up resistor in-circuit |
| 4 |     | PS-EN | LDO39050 Enable | Input (Active HIGH, pull-down resistor in-circuit) |
| 5 | IO5 | PD-EN | Presence Detection Enable | Input (User defined) |
| 6 | IO4 | PD-Out | Presence Detected | Output (User defined) |

### FFC Expansion Connector
10 position 1.0mm pitch FFC connector providing 3.3v regulated power, I2C and 6 additional IO as designed for use with ToF Sensor

| Pin | ESP32-C3 IO | Function | Description | Pin Settings Requirements |
| --- | ----------- | -------- | ----------- | -------------------------- |
| 1   |      | 3v3 | Sensor Power |
| 2   |      | GND | Ground | |
| 3   | IO2  | SDA | I2C Data |
| 4   | IO3  | SCL | I2C Clock |
| 5   | IO7  | VL53-PWR | High Side Power Switch (on VL53 breakout) | as Output (Active HIGH) |
| 6   | IO9  | VL53-Int | VL53L5 Interrupt | as Input (Active LOW) |
| 7   | IO6  | VL53-I2C-RST | VL53L5 I2C Reset | as Output (Active HIGH) |
| 8   | IO8  | VL53-LPn | VL53L5 Low Power Enable |as Output (Active LOW) |
| 9   | IO0  | PD-LED1 | NO Presence Detection Indicator | as Output (Active HIGH) |
| 10  | IO10 | PD-LED2 | Presence Detected Indicator | as Output (Active HIGH) |

### STEMMA QT / Qwiic
JST SH style connector, 1.0mm Pitch, 4 Position

| Pin | ESP32-C3 IO | Function | Description |
| --- | ----------- | -------- | ----------- |
| 1 |  | GND | Ground |
| 2 |  | 3v3 | Voltage Out |
| 3 | IO2 | SDA | I2C Data |
| 4 | IO3 | SCL | I2C Clock |

### Program/Debug Contact Pads
[Kyocera AVX 009258008004064](http://datasheet.octopart.com/009258008004064-KYOCERA-AVX-datasheet-165279551.pdf), 1.0mm Pitch 8 Position single piece connector. An optional programming adapter is available.

| Pin | ESP32-C3 IO | Function | Description | Pin Settings Requirements |
| --- | ----------- | -------- | ----------- | -------------------------- |
| 1 |  | GND | Ground | |
| 2 |  | 5v | Power | 3.5 -5.5vdc |
| 3 | EN | ESP32-C3 Enable | Active LOW to Reset ESP32-C3 |
| 4 | IO9 | Boot | ESP32-C3 Bootloader | Active LOW during Reset to enter Bootloader |
| 5 | IO20 | RXDO | Serial UART Receive | |
| 6 | IO21 | TXDO | Serial UART Transmit | |
| 7 |  | PS-EN | LDO39050 Enable | Input (Active HIGH = EN, pull-down resistor in-circuit) |
| 8 | IO5 | PD-EN | Presence Detection Enable | As Input (User defined) |

### ESP32-C3 Pins Used Internally

| ESP32-C3 IO | Function | Description | Pin Settings Requirements |
| ----------- | -------- | ----------- | -------------------------- |
| IO1 | SEC_EN | OPTIGA Trust-M Enable | Output (Active HIGH=EN, pull-up resistor in-circuit) |
| IO18 | PG | Power Good signal from LD39050 | Input (HIGH when good, pull-up resistor in-circuit) |
| IO19 | LED | ESP32-C2 Blue User Indicator | Output (Active HIGH = ON) |

