# Thrust-Stand-and-Wind-Tunnel-Controller
4-layer STM32F4-based thrust stand + wind tunnel controller PCB equipped with 24-bit ADS1220 load cell signal amplifiers. Rated for 4S-6S LiPo battery (16.8V - 25.2V), and 70A max current.

## What this project is about
Selecting the right brushless motor requires accurate, reliable data on thrust and RPM under real operating conditions. This board was built to solve that problem by acting as a complete controller and telemetry hub for propulsion testing.

At its core, the board drives the electronic speed controller while monitoring system performance in real time. It features integrated high-side voltage sensing along with a precision current shunt rated for up to 70A continuous measurements.

- Power management is handled entirely onboard through a multi-stage regulation pipeline:
- A primary buck converter steps high-voltage battery power down to a stable 5V rail.
- A 3.3V low-dropout regulator supplies power to the STM32 microcontroller and digital logic.
- A dedicated, ultra-low-noise 4.3V LDO powers the load cell front-end to ensure clean analog signal acquisition.
- USB-C input for 5V power and serial debugging.
- Features a power MUX that chooses the 5V input between the buck and the USB-C.

For multi-axis motion and environmental tracking, the board exposes three independent I2C buses, allowing simultaneous connection of up to three magnetic rotary encoders and two external IMUs. Live test results are streamed off the board through an onboard UART wireless telemetry module, eliminating the need for trailing cables during high-RPM testing.

## Hardware Details
<img width="670" height="521" alt="Screenshot 2026-09-01 210434" src="https://github.com/user-attachments/assets/ca8c5874-6275-48d0-b4aa-69e2c0881060" />
<img width="554" height="433" alt="Screenshot 2026-09-01 210748" src="https://github.com/user-attachments/assets/e30bf5c3-fd98-470d-9d62-6eefac28f8ae" />

- 4-layer
- 25.2V / 70A Maximum
- Buck converter with internal FETs (LM61480RPHR) from 25.2V down to 5V
- Fixed 3V3 voltage output LDO (TLV75733PDYDR) from 5V line
- Adjustable output voltage LDO (TPS79501QDRBRQ1) from 5V line

## Schematic
Schematic
### Main Schematic
<img width="863" height="363" alt="Main Schematic" src="https://github.com/user-attachments/assets/b717d983-a377-4212-98d0-3ee1b86df8ea" />

### Input Connectors and Sensors Schematic
<img width="887" height="536" alt="Input Connectors and Sensors Schematic" src="https://github.com/user-attachments/assets/81306762-63df-42c6-87d8-e531c8290234" />

### Buck Converter Schematic
<img width="915" height="256" alt="Buck Converter Schematic" src="https://github.com/user-attachments/assets/63e2ed8a-0cc9-4e70-9fcd-17bbd31fe8d2" />

### USB-C Schematic
<img width="733" height="514" alt="USBC Schematic" src="https://github.com/user-attachments/assets/f8f167ac-b963-4a1b-ba38-05563303c078" />

### Power Shifter Schematic
<img width="905" height="397" alt="Power Shifter Schematic" src="https://github.com/user-attachments/assets/788adec1-982b-4651-9d64-04dd325f2a0b" />

### LDO 3V3 Schematic
<img width="853" height="295" alt="LDO 3V3 Schematic" src="https://github.com/user-attachments/assets/701ceb0c-4388-4b77-b7be-95b452f4e8c3" />

### LDO 4V3 Schematic
<img width="841" height="362" alt="LDO 4V3 Schematic" src="https://github.com/user-attachments/assets/8503b4d4-f9b9-48cd-9980-c899dea62209" />

### MCU and Output Connectors Schematic
<img width="846" height="623" alt="MCU and Output Connectors Schematic" src="https://github.com/user-attachments/assets/c53a8831-67d8-4b45-9966-2d5be754bbc3" />

## Layers
The board consists of 4 layers:
1. Layer 1: POWER/SIG
2. Layer 2: GND
3. Layer 3: GND/POWER
4. Layer 4: SIG

### Layer 1
This layer consists of all the power converters (Buck + LDOs), Connectors, USB-C, and the voltage and current sensing amplifiers.

<img width="717" height="557" alt="Layer 1" src="https://github.com/user-attachments/assets/bb82f150-39a8-4312-8545-a465c10ea714" />

### Layer 2
Solid GND plane to minimize heat dissipation and reduce the return current for the buck converter and LDOs.

<img width="735" height="569" alt="Layer 2" src="https://github.com/user-attachments/assets/a9279b52-9429-4b9b-8ff8-a410a524dd29" />

### Layer 3
GND plane + power plane to increase the current rating of the board

<img width="723" height="563" alt="Layer 3" src="https://github.com/user-attachments/assets/56cce76a-5929-442e-8aa4-8d4dde7d0225" />

### Layer 4
This layer consists of the main MCU (STM32F446RET6), the load cell amplifiers (ADS1220), and all the signal traces. (Routing currently still in progress)

<img width="707" height="569" alt="Layer 4" src="https://github.com/user-attachments/assets/3144e157-bf3c-470a-ad39-6d8620656b8e" />




