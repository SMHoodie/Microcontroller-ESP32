# Microcontroller-ESP32

🚀 Updated Version Available! 🚀
This repository contains the first version of the ESP32 Custom Board.
A new refined version with improved power management and UART communication.
https://mud-barge-6df.notion.site/ESP32-Microcontroller-1977578929b6800c9e9beba360cbae37
# 📜 Components You'll Need for Your Custom ESP32 Board

Here are the essential components for designing your custom ESP32 board, along with their roles and key points.

---

## 1. ESP32-WROOM-32E-N8 (Main Microcontroller)

- Role: This module is the heart of your board, handling all processing tasks, Wi-Fi/Bluetooth communication, and GPIO control.
- Key Points:
    - Operates at 3.3V.
    - Features built-in flash memory for program storage.
    - Provides multiple GPIOs for peripheral connections.
    - Supports UART, SPI, I2C, and PWM communication protocols.

---

## 2. USB-C Connector (4 Pins)

- Role: Used for both programming the ESP32 and powering the board.
- Key Points:
    - Contains VBUS (5V), GND, D+, and D- pins.
    - Supports USB-to-serial communication using a CP2102N chip.
    - Protection: Includes 5.1 kΩ pull-up resistors on D+ and D- for proper USB enumeration.

---

## 3. Voltage Regulator (AMS1117-3.3)

- Role: Converts 5V USB input into a stable 3.3V for the ESP32.
- Key Points:
    - Requires 22µF capacitors at both input and output for stabilization.
    - VIN (input) is connected to 5V USB-C VBUS.
    - VOUT (output) supplies 3.3V to the ESP32.

---

## 4. Two Switch Buttons (EN and BOOT)

- Role:
    - EN (Enable Button): Resets the ESP32.
    - BOOT (GPIO0 Button): Forces bootloader mode for firmware flashing.
- Key Points:
    - EN pin is pulled HIGH via a 10kΩ pull-up resistor to 3.3V.
    - BOOT pin (GPIO0) is pulled HIGH via a 10kΩ pull-up resistor but is pulled LOW when pressed.

---

## 5. USB to Serial Converter (CP2102N)

- Role: Provides USB-to-serial communication for flashing firmware onto the ESP32.
- Key Points:
    - Converts USB signals (D+ and D-) to UART (TXD, RXD) for the ESP32.
    - DTR (Data Terminal Ready) and RTS (Request to Send) are used for automatic reset and boot mode entry.
    - Works with 3.3V logic levels to match the ESP32.

---

## 6. Resistors

- Role: Used for pull-ups, current limiting, and circuit stabilization.
- Key Components:
    - 5.1kΩ → USB D+ and D- pull-up resistors.
    - 10kΩ → Pull-up resistors for EN and BOOT.
    - 22Ω → Series resistors for USB data lines.
    - 1kΩ & 560Ω → Current-limiting resistors for LEDs.

---

## 7. Capacitors

- Role: Filters noise and stabilizes power.
- Key Components:
    - 100nF → Close to ESP32 power pins for decoupling.
    - 22µF → Bulk capacitors for power regulation.
    - 10µF & 4.7µF → Power filtering capacitors.

---

## 8. Transistors

- Role: Controls high-power circuits like reset logic and USB handling.
- Key Components:
    - SS8050-G (NPN) → Used for reset circuit switching.
    - 2N7002T-7-F (MOSFET) → Handles USB signals.

---

## 9. ESD Protection Diodes

- Role: Protects sensitive components from electrostatic discharge (ESD).
- Key Components:
    - 5D5.0CT1G → USB overvoltage protection.

---

## 10. LED Indicators

- Role: Visual feedback for power and status.
- Key Components:
    - Green LED (19-218/G7C-BK1L2B7Y) → Power indicator (3.3V).
    - Red LED (17-21URC/TR8) → Boot or data activity indicator.

---

## 11. Pin Headers

- Role: Provides access to GPIOs and communication pins.
- Key Points:
    - Includes VCC, GND, TX, RX, EN, and GPIO pins.
    - Uses 2.54mm standard spacing for compatibility.
