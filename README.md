# UKSEDS Olympus Rover Trials

<div align="center">

![Rover Banner](https://github.com/user-attachments/assets/c37ebeb1-6d72-45ad-b963-1364806cb4b6)

**An autonomous planetary rover prototype with advanced sensor fusion and computer vision capabilities**

[![Python](https://img.shields.io/badge/Python-3.x-blue.svg)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-Web_Control-green.svg)](https://flask.palletsprojects.com/)
[![OpenCV](https://img.shields.io/badge/OpenCV-Computer_Vision-red.svg)](https://opencv.org/)


</div>

---

## 📖 Overview

Welcome to **MANN-E Rover** – a custom-built planetary rover developed for the UKSEDS Olympus Rover Trials! This repository contains the complete software stack for an autonomous and remotely operated rover prototype, featuring advanced hardware control, sensor fusion, a Flask-based web interface, and robust computer vision capabilities.

---

## ✨ Key Features

<table>
<tr>
<td width="50%">

### Control Dashboard
- Live video streaming
- Real-time sensor telemetry
- Manual & automated mission controls
- Intuitive web interface

**Tech:** `Flask`, `HTML/CSS`, `JavaScript`

</td>
<td width="50%">

### Autonomous Navigation
- Precise odometry calculations
- Turn-then-drive sequences
- 2D pose estimation (X, Y, θ)
- Mission path execution

**Tech:** `Python`, `Kinematics Engine`

</td>
</tr>
<tr>
<td width="50%">

### Sensor Fusion
- IMU + Encoder integration
- Roll/Pitch monitoring
- Absolute distance tracking
- Real-time pose updates

**Tech:** `I2C`, `Serial Communication`

</td>
<td width="50%">

### Computer Vision
- Camera servo control
- QR code detection
- Video stream processing
- Automated scanning

**Tech:** `OpenCV`, `Computer Vision`

</td>
</tr>
</table>

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    Web Dashboard (Flask)                │
│               Telemetry • Controls • Video              │
└────────────────────────┬────────────────────────────────┘
                         │
          ┌──────────────┴──────────────┐
          │                             │
┌─────────▼─────────┐         ┌────────▼────────┐
│  Python Control   │         │  Computer Vision │
│   • Kinematics    │◄────────┤   • QR Detection │
│   • Automation    │         │   • Camera Servo │
│   • Sensor Fusion │         └─────────────────┘
└─────────┬─────────┘
          │
┌─────────▼─────────────────────────────────────┐
│         Hardware Layer (Arduino C++)          │
│    Motors • IMU • Encoders • Servos          │
└───────────────────────────────────────────────┘
```

---

## 🚀 Quick Start

### Prerequisites

- **Raspberry Pi 4/5** with SSH enabled
- **Python 3.x**
- Hardware: Motors, IMU, Encoders, Camera, Servo

### Installation

**1. Clone the repository**
```bash
git clone https://github.com/gokulsp1995/rover-code.git
cd rover-code
```

**2. Install dependencies**
```bash
pip3 install flask opencv-python-headless RPi.GPIO smbus
```

**3. Launch the control dashboard**
```bash
python3 app.py
```

**4. Access the interface**
```
Open your browser: http://<your_pi_ip_address>:5000
```

---

## 🔧 Connection Guide

<details>
<summary><b>Click to expand setup instructions</b></summary>

### Network Setup
1. Connect both Pi and laptop to the **same WiFi network**
2. Find your Pi's IP address or use `raspberrypi.local`

### SSH Connection
```bash
# Using hostname
ssh gokul@raspberrypi.local

# Or using IP address
ssh gokul@<pi_ip_address>
```

### Running the Application
```bash
cd ~/Desktop/MANN-E/
python3 app.py
```

</details>

---

## 📂 Project Structure

| Component | Files | Description |
|-----------|-------|-------------|
| **Web Interface** | `app.py`, `index.html`, `style.css` | Flask server & control dashboard |
| **Autonomy** | `automation_controller.py`, `kinematics.py` | Mission planning & execution |
| **Sensors** | `imu.py`, `encoders.py`, `hardware.py` | Sensor fusion & data processing |
| **Vision** | `qr.py`, `camera_scan_controller.py`, `servo_cam.py` | Computer vision & scanning |
| **Communication** | `serial_comm.py`, `heartbeat.py` | Hardware interface & health monitoring |

---


## 🎥 Media & Demos

<div align="center">

### Sand Testing at Airbus Facility
<img width="1280" height="800" alt="rover" src="https://github.com/user-attachments/assets/2e0946e9-f2fc-49b4-9b03-b9b11fcaa8ca" />


</div>

---

## Contributing

We welcome contributions! Here's how you can help:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## Key Milestones

| Feature | Status | Description |
|---------|--------|-------------|
| Auto Camera Tilt | ✅ Complete | Full camera control for autonomous scanning |
| Automation System | ✅ Complete | End-to-end autonomous mission execution |
| OOP Refactor | ✅ Complete | Object-oriented kinematics model |
| Sensor Fusion | ✅ Complete | IMU integration with roll/pitch/yaw |
| Manual Control | ✅ Complete | Stable web-based manual operation |

---

## Contact & Support

- **Found a bug?** [Open an issue](https://github.com/gokulsp1995/rover-code/issues)
- **Have a suggestion?** [Start a discussion](https://github.com/gokulsp1995/rover-code/discussions)
- **Email:** gokulsp2020@outlook.com

---


---

<div align="center">

**Built for UKSEDS Olympus Rover Trials**

⭐ Star this repo if you find it helpful!

[⬆ Back to Top](#ukseds-olympus-rover-trials---mann-e-rover)

</div>
