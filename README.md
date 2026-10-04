# Sulfex
# Bi₂O₃-Based H₂S Sensor

## Overview

A prototype simulation of a Bi₂O₃-based colorimetric H₂S sensing system.
The simulation uses an ESP32 to process a simulated chemical sensing input
and provides visual status indication through LEDs and an OLED display.

## System Architecture

H₂S
 ↓
Bi₂O₃ Sensing Strip
 ↓
Optical/Electrical Readout
 ↓
ESP32
 ↓
OLED + LED Status Indication

## Simulation

Since the actual Bi₂O₃ sensing strip and optical sensor are not available
in the simulation environment, a potentiometer is used to simulate the
sensor response.

### Status Levels

| Simulated Level | Status | Indicator |
|---|---|---|
| 0–19% | SAFE | Green LED |
| 20–49% | EXPOSURE | Yellow LED |
| 50–100% | HIGH | Red LED |

## Components

- ESP32 DevKit
- DHT22 Temperature/Humidity Sensor
- SSD1306 OLED Display
- DS1307 RTC
- Potentiometer
- Green LED
- Yellow LED
- Red LED
- 220 Ω Resistors

## Pin Configuration

| Component | ESP32 Pin |
|---|---|
| DHT22 Data | GPIO 4 |
| Potentiometer | GPIO 34 |
| OLED SDA | GPIO 21 |
| OLED SCL | GPIO 22 |
| RTC SDA | GPIO 21 |
| RTC SCL | GPIO 22 |
| Green LED | GPIO 26 |
| Yellow LED | GPIO 27 |
| Red LED | GPIO 25 |

## Simulation Files

- [Arduino Code](./simulation/sketch.ino)
- [Circuit Diagram](./simulation/diagram.json)
- [Simulation Video](./H2S%20Simulation.mp4)

## How It Works

The potentiometer represents the response of the chemical sensing element.
Its value is read by the ESP32 and converted into a simulated H₂S response
from 0–100%.

The ESP32 classifies the response into three states:

- SAFE
- EXPOSURE
- HIGH

The corresponding LED is activated and the OLED displays the sensor status,
temperature, humidity, and real-time clock.

## Important Note

The simulated 0–100% value does not represent an actual H₂S concentration
in ppm. Experimental calibration is required to establish the relationship
between the Bi₂O₃ sensor response and actual H₂S concentration.

## Future Improvements

- Integrate the actual Bi₂O₃ sensing strip
- Add an RGB/color sensor
- Develop experimental calibration
- Convert sensor response to H₂S concentration
- Implement image/color processing
- Validate the system using controlled laboratory measurements
