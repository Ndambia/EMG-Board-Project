# 3-Channel EMG Data Acquisition System (ESP32-Based)

## Overview

This project is a **3-channel Electromyography (EMG) Data Acquisition (DAQ) system** built around an **ESP32 MCU**. It is designed to acquire low-level biopotential signals from muscles, condition them using an analog front-end, digitize them via an external ADC, and transmit or store the data for further processing.

The system is modular and portable, integrating power management for battery operation, making it suitable for wearable and embedded biomedical applications.

---

## Key Features

* Three independent EMG input channels
* External multi-channel ADC with I²C interface
* ESP32 MCU for control, DSP, and communication
* Li-Po battery charging support
* Boost / regulation circuitry for stable operation
* Compact PCB designed for embedded and wearable use

---

## System Architecture

### Signal Chain Overview

```
Muscle Electrodes
      ↓
EMG Analog Front-End (DAQ)
      ↓
External ADC (3 Channels)
      ↓  I²C
ESP32 MCU
      ↓
USB / BLE / Wi-Fi 
```

---

## Functional Block Description

### 1. EMG DAQ (Analog Front-End)

* Three independent EMG channels
* Powered at **3.3 V**
* Outputs conditioned analog signals suitable for ADC input

**Typical functionality includes:**

* Instrumentation amplification
* High-pass filtering to remove motion artifacts
* Low-pass filtering to reduce high-frequency noise
* Optional 50/60 Hz notch filtering

---

### 2. Analog-to-Digital Converter (ADC)

* Powered at **3.3 V**
* Three analog input channels
* Digital interface: **I²C (SDA, SCL)**

The ADC digitizes the conditioned EMG signals for processing by the ESP32.

---

### 3. Microcontroller Unit (ESP32)

* Powered at **3.3 V**
* Configures and reads data from the ADC
* Performs optional digital signal processing (RMS, envelope extraction)
* Supports USB, BLE, and Wi-Fi communication

---

### 4. Power Management

#### Li-Po Battery Charger

* Supports single-cell Li-Po batteries
* USB-powered charging
* Enables portable operation

#### Boost / Regulation Circuit

* Maintains stable system voltage during battery discharge
* Ensures reliable operation of analog and digital blocks

---

## PCB Design

### PCB Back Layer

![PCB Back](PCB%20Image/Layout%20Back.png)
The back layer shows the ground plane distribution and return paths. Care was taken to maintain a low-impedance ground for the analog EMG front-end to minimize noise coupling from digital sections.

### PCB Front Layer

![PCB Front](PCB%20Image/Layout%20Front.png)
The front layer contains the majority of signal routing and component placement. Analog EMG paths are kept short and isolated from high-speed digital and power traces.

### PCB Routing Overview

![PCB Layout](PCB%20Image/PCB%20rayout.png)
This image provides an overall routing overview, highlighting trace organization, separation between analog and digital domains, and controlled routing for sensitive EMG signals.

### Routing – Front

![Routing Front](PCB%20Image/Routing%20Front.png)
The front routing layer illustrates how EMG signal traces are carefully routed with minimal vias to reduce interference and preserve signal integrity.

### Routing – Back

![Routing Back](PCB%20Image/Routes%20Back.png)
Back-side routing is primarily used for ground returns and power distribution, helping to maintain clean reference planes for low-noise acquisition.

### PCB 3D View

![PCB 3D](PCB%20Image/PCB%203D.png)
The 3D view shows overall board dimensions, component height clearance, and suitability for enclosure or wearable integration.

### PCB Front 3D View

![PCB Front 3D](PCB%20Image/PCB%20Front%203D.png)
This view highlights top-side component placement, including the ESP32 module, ADC, and EMG front-end circuitry.

### PCB Back 3D View

![PCB Back 3D](PCB%20Image/PCB%20Back%203D.png)
The back-side 3D view shows passive components, ground stitching vias, and mechanical layout considerations.

### Design Progress Snapshot

![Progress](PCB%20Image/Progress.png)
This image documents the PCB design progress during layout and routing stages.

### Schematics

![Schematics](PCB%20Image/Schematics.png)
The schematic captures the complete system design, including EMG analog front-end, ADC, ESP32 MCU, and power management circuitry.

---

## Intended Applications

* Multi-channel EMG signal acquisition
* Wearable biomedical research devices
* Prosthetics and rehabilitation research
* Gesture recognition and HMI systems
* Academic and laboratory EMG experimentation

---

## Design Notes & Safety

* Proper analog grounding and shielding are critical for low-noise EMG acquisition
* Use shielded electrode cables where possible
* This system is intended for **research and educational use only**
* Not certified for clinical or diagnostic applications

---

## Author

**Eng. Ndambia M.**
MyGen Solutions

---

## License & Disclaimer

This project is provided for **research and educational purposes only**. It is not a certified medical device and must not be used for clinical diagnosis or treatment.
