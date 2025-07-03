# RFID Door Lock System

An Arduino-based door locking system that uses RFID authentication to control a servo motor for locking and unlocking a door.

## 🛠️ Features

- Uses MFRC522 RFID module to scan RFID cards.
- Controls a servo motor to open or lock the door.
- Provides serial output for monitoring access.
- Easy to modify or extend with more RFID tags.

## 🧰 Components Required

- Arduino Uno (or compatible)
- MFRC522 RFID Reader
- Servo Motor (e.g., SG90)
- Breadboard and Jumper Wires
- Power Supply (or USB connection)
- RFID Tags/Cards

## 🔌 Circuit Connections

| MFRC522 | Arduino |
|---------|---------|
| SDA     | D10     |
| SCK     | D13     |
| MOSI    | D11     |
| MISO    | D12     |
| IRQ     | Not Connected |
| GND     | GND     |
| RST     | D9      |
| 3.3V    | 3.3V    |

| Servo   | Arduino |
|---------|---------|
| Signal  | D8      |
| VCC     | 5V      |
| GND     | GND     |

## 🧠 How It Works

1. System waits for an RFID card.
2. When a valid card is scanned, the servo motor rotates to unlock the door.
3. After a short delay, the door locks again.

## 🔒 Security

You can update the allowed RFID UIDs in the sketch code by modifying this section:

```cpp
byte allowedUID[] = {0xXX, 0xXX, 0xXX, 0xXX}; // Replace with your RFID UID
