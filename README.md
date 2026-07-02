# Edge AI Light Classification System using Raspberry Pi Pico W

## Overview

The **Edge AI Light Classification System** is an intelligent embedded systems project developed on the **Raspberry Pi Pico W**. The system continuously monitors ambient light using three **Light Dependent Resistor (LDR)** sensors, performs real-time statistical analysis on-device, and classifies environmental lighting conditions without relying on cloud computing or external processing.

Designed around core **Edge AI** principles, the system employs adaptive statistical modeling, multi-sensor data fusion, and dynamic thresholding to provide accurate and reliable light classification. Visual feedback is delivered through a **16×2 I2C LCD** and an **RGB LED**, enabling intuitive real-time monitoring.

---

# Key Features

* Real-time ambient light monitoring using three LDR sensors
* Automatic sensor calibration during startup
* Multi-sensor data fusion for improved measurement accuracy
* Adaptive light classification using statistical analysis
* Dynamic thresholding based on environmental conditions
* Continuous learning through adaptive baseline updates
* Flicker detection for unstable lighting conditions
* Live status display on a 16×2 I2C LCD
* RGB LED indication of lighting states
* Fully offline operation on the Raspberry Pi Pico W

---

# Hardware Components

* Raspberry Pi Pico W
* 3 × Light Dependent Resistors (LDRs)
* 16×2 I2C LCD Display
* RGB LED (Common Cathode)
* Resistors
* Breadboard
* Jumper Wires
* USB Cable

---

# Software Requirements

* MicroPython
* Thonny IDE

---

# Hardware Connections

## LDR Sensors

| Component | Raspberry Pi Pico W Pin |
| --------- | ----------------------- |
| LDR 1     | GP26 (ADC0)             |
| LDR 2     | GP27 (ADC1)             |
| LDR 3     | GP28 (ADC2)             |

### I2C LCD Display

| LCD Pin | Raspberry Pi Pico W Pin |
| ------- | ----------------------- |
| SDA     | GP0                     |
| SCL     | GP1                     |
| VCC     | 3.3V                    |
| GND     | GND                     |

### RGB LED

| LED Color | Raspberry Pi Pico W Pin |
| --------- | ----------------------- |
| Red       | GP16                    |
| Green     | GP17                    |
| Blue      | GP18                    |

---

# Project Resources

### Source Code

[click here to](code/Self_Calibrating_Ambient_Light_Classifier_main_code.py) Access the complete project source code in this repository.

### Demonstration

A demonstration video showcasing the system's operation is included in the project files.

---

# System Operation

## 1. Automatic Calibration

Upon startup, the Raspberry Pi Pico W performs an automatic calibration routine by collecting multiple sensor samples.

The calibration process computes:

* Mean
* Variance
* Standard Deviation

These statistical values establish the baseline used for subsequent light classification.

---

## 2. Multi-Sensor Data Fusion

Rather than relying on a single sensor, the system combines measurements from all three LDRs using weighted averaging:

**Average Light = (LDR1 × 0.5) + (LDR2 × 0.2) + (LDR3 × 0.3)**

This approach minimizes sensor noise and improves measurement reliability.

---

## 3. Real-Time Statistical Analysis

The system continuously evaluates:

* Average light intensity
* Sensor variance
* Historical lighting trends

These parameters are processed to determine the current lighting condition.

---

## 4. Environment Classification

The detected lighting state is displayed on the LCD while the RGB LED provides an immediate visual indication.

| Lighting State   | RGB LED |
| ---------------- | ------- |
| Bright           | Green   |
| Dim              | Blue    |
| Dark             | Red     |
| Flicker Detected | Yellow  |

---

## 5. Adaptive Learning

To maintain long-term accuracy, the system continuously updates its statistical model, allowing it to gradually adapt to changing ambient lighting conditions without requiring manual recalibration.

---

# Light Classification Logic

### Bright

Triggered when the measured average light intensity exceeds the calculated upper threshold.

### Dim

Represents the normal operating range between the upper and lower thresholds.

### Dark

Detected when the average light intensity falls below the calculated lower threshold.

### Flicker

A flicker condition is identified when:

* Significant differences exist between sensor readings, or
* Rapid fluctuations in ambient light occur within a short period.

---

# Technical Highlights

* Edge AI-inspired embedded intelligence
* Multi-sensor data fusion
* Adaptive thresholding
* Statistical signal processing
* Continuous learning
* Decision-based classification
* Flicker detection
* Real-time embedded monitoring
* Hardware and software integration
* Efficient on-device computation

---

# Skills Demonstrated

* Raspberry Pi Pico W Programming
* Embedded Systems Development
* MicroPython
* Analog-to-Digital Converter (ADC) Programming
* GPIO Programming
* I2C Communication
* LCD Interface Development
* RGB LED Control
* Sensor Fusion Techniques
* Statistical Data Analysis
* Real-Time Embedded Programming
* Edge AI Fundamentals

---

# Project Structure

```text
Edge-AI-Light-Classification-System-Raspberry-Pi-Pico-W/
│
├── main.py
├── lcd_api.py
├── pico_i2c_lcd.py
├── README.md
├── images/
│   ├── hardware.jpg
│   ├── lcd_display.jpg
│   └── wiring.jpg
└── demo.mp4
```

---

# Future Enhancements

* OLED display support
* SD card data logging
* Wi-Fi-enabled dashboard
* Web-based monitoring interface
* Machine learning model integration
* Ambient light prediction
* MQTT-based remote monitoring
* Sensor diagnostics and health monitoring

---

# Author

**Muhammad Musa**

**Computer Engineering Student | Embedded Systems | Edge AI | IoT | Raspberry Pi Pico W | MicroPython**

Passionate about designing intelligent embedded systems and developing real-world solutions at the intersection of hardware, software, and artificial intelligence.
