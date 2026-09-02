# Thrust-Stand-Wind-Tunnel-Controller
4-layer STM32F4-based thrust stand + wind tunnel controller PCB equipped with 24-bit ADS1220 load cell signal amplifiers. Rated for 4S-6S LiPo battery (16.8V - 25.2V), and 70A max current.

## What this project is about
Selecting the right brushless motor requires accurate, reliable data on thrust and RPM under real operating conditions. This board was built to solve that problem by acting as a complete controller and telemetry hub for propulsion testing.

At its core, the board drives the electronic speed controller while monitoring system performance in real time. It features integrated high-side voltage sensing along with a precision current shunt rated for up to 70A continuous measurements.

- Power management is handled entirely onboard through a multi-stage regulation pipeline:
- A primary buck converter steps high-voltage battery power down to a stable 5V rail.
- A 3.3V low-dropout regulator supplies power to the STM32 microcontroller and digital logic.
- A dedicated, ultra-low-noise 4.3V voltage reference IC powers the load cell front-end to ensure clean analog signal acquisition.

For multi-axis motion and environmental tracking, the board exposes three independent I2C buses, allowing simultaneous connection of up to three magnetic rotary encoders and two external IMUs. Live test results are streamed off the board through an onboard UART wireless telemetry module, eliminating the need for trailing cables during high-RPM testing.

## Hardware Details
<img width="670" height="521" alt="Screenshot 2026-09-01 210434" src="https://github.com/user-attachments/assets/ca8c5874-6275-48d0-b4aa-69e2c0881060" />
<img width="554" height="433" alt="Screenshot 2026-09-01 210748" src="https://github.com/user-attachments/assets/e30bf5c3-fd98-470d-9d62-6eefac28f8ae" />

- 4-layer
- 25.2V / 70A Maximum
- Buck converter from 25.2V down to 5V
- Fixed 3V3 voltage output LDO (TLV75733PDYDR) from 5V line
- Adjustable output voltage LDO (TPS79501QDRBRQ1) from 5V line
