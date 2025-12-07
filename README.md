# RF-Vector-Sweeper 📡


## 📄 What It Is
A rotating, multi-sensor system that acts like a radar—without the complexity of real radar hardware! 🛠️  
Combining servos, nRF24 modules, distance sensors, and input devices, it measures RF signal strength, uses servo angles for direction, and provides feedback via vibration, LEDs, or displays.  
Not a physical radar (no HF mixers here 😉), but a directional RF sweep system with "radar-like feel"!

---


## ✨ Key Features (What It Does)

| Feature | Description | Emoji |
|---------|-------------|-------|
| Rotating Scanner | Servo-driven mechanical rotation—scans like a radar dish! | 🔄 |
| RF Signal Strength | Measures RSSI via nRF24 modules—stronger signals mean closer transmitters. | ⚡ |
| Sensor Fusion | Optional integration with ultrasonic/ToF distance sensors for spatial mapping. | 🗺️ |
| User Input | Configurable via potentiometer (adjust scan speed) and 5-way button (switch modes). | 🎮 |
| Haptic/Optical Feedback | Vibration (proportional to signal strength) + LED ring (visualizes angle). | 🌟 |

---

## 🛠️ Hardware Components (That i used )

| Component | Quantity | Purpose |
|-----------|---------|---------|
| ESP32 | 1 | Main controller (Linux/PlatformIO toolchain, WLAN, GPIO/SPI support). |
| Raspberry Pi Pico | 1 (optional) | Backup/secondary microcontroller for flexibility. |
| Arduino Nano | 1 (optional) | Additional I/O or prototyping support. |
| nRF24L01 Modules | 2 | Wireless signal reception/transmission + RSSI measurement. |
| 2 DOF Servo/Hand | 1 | Mechanical rotation for directional scanning (0-180° range). |
| Potentiometer | 1 | Adjust scan speed (analog input). |
| 5-Way Navigation Button | 1 | Switch between scan/calibrate/stop modes (digital input). |
| TJA1050 CAN-Bus Transceiver | 1 (optional) | For CAN bus communication (if extended sensor networks are needed). |
| CD4051 Analog Multiplexer | 1 (optional) | Expand analog sensor inputs (e.g., additional environmental sensors). |
| Vibration Motor | 1 | Haptic feedback (intensity proportional to signal strength). |
| Distance Sensors (Ultrasonic/ToF) | 1 (optional) | Measure distance to objects (complements RF direction data). |
| Camera (WIP) | 1 | Fixed-soldered pins (currently non-functional; future integration planned). |

---

## 🚀 Roadmap (Development Plan)

| Step | Objective | Status | Description |
|------|-----------|--------|------------|
| 1 | ESP32 Setup (PlatformIO/Linux) | ✅ Complete | Toolchain configured, board detected, WLAN/GPIO/SPI initialized. |
| 2 | nRF24L01 Module Operation | ❌ In Progress | SPI initialization, CE/CSN pin wiring, RX/TX testing, RSSI display. |
| 3 | Mechanical Servo Scanner Build | ❌ Pending | Mount servo, PWM control for angle rotation, integrate RF measurements per angle. |
| 4 | Input Device Integration | ❌ Pending | Map potentiometer to scan speed, 5-way button for mode switching, CD4051 for analog expansion. |
| 5 | Distance Sensor Addition | ❌ Pending | Integrate ultrasonic/ToF sensor, combine RF direction + distance for spatial mapping. |
| 6 | Output Feedback Implementation | ❌ Pending | Vibration (PWM-controlled intensity), LED ring (angle visualization), optional audio. |
| 7 | GitHub Project Setup | ❌ Pending | Create repo (e.g., RF-Vector-Sweeper, SpectraSpin), add README, schematics, code, videos/GIFs. |

---

## 🌟 Vision (Long-Term Goals)
- **Doppler Experimentation:** Explore signal frequency shifts (if possible with consumer modules). 🧪  
- **Enhanced Radar-Like Features:** Future plans to add HF mixers, I/Q demodulation, or frequency sweeps for deeper RF analysis. 🔍  
- **UAV Integration:** Mount the system on a drone platform for "flying sensor head" mobility. 🚁  

---

## ⚠️ Important Notes
- **nRF24L01 Limitations:** These modules only provide RSSI and packet data—no raw HF signal access. Real radar requires mixers, local oscillators (LO), and I/Q processing (not feasible with consumer modules). 😊  
- **Camera WIP:** Fixed-soldered pins prevent current use. Let us know if you have tips for rework (e.g., desoldering/resoldering)! 🛠️  
- **Servo Precision:** Verify 0-180° range and stability—calibrate if needed to avoid misalignment. ⚠️  

---


## 🤝 How to Contribute
- **Ideas:** Open an issue with suggestions. 💬  
- **Code:** Submit pull requests to improve functionality. 🐱💻  
- **Hardware Tips:** Share advice (especially for camera fixes) via comments! 🛠️  

---

## 📜 License
MIT License—use, modify, and share freely, but credit the project! 🌱  

*"Scan, measure, feel—RF Vector Sweeper makes RF signals tangible!"* 🌍✨
