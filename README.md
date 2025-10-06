# A-ORT

Connect the Pi and the laptop to the same wifi

In PuTTy, type: raspberrypi.local

ssh gokul@<pi_ip_address>
cd ~/Desktop/MANN-E/

In terminal, run:  python app.py

UKSEDS Olympus Rover Trials 🛰️

⭐ Overview

Welcome to the repository for the MANN-E Rover system, a custom-built planetary rover developed for the UKSEDS Olympus Rover Trials.

This project represents the complete software stack for an autonomous and remotely operated rover prototype. The system integrates advanced hardware control, sensor fusion (IMU + Encoders), a Flask-based web control interface, and a robust computer vision pipeline for environmental interaction.

⚙️ Key Features & Technical Stack

The rover's architecture relies on Python 3 for high-level control and Arduino C++ for low-level motor/sensor management, communicating via serial.
Feature Area	Key Functionality	Core Files & Technology
Control Dashboard (GUI)	Live video feed, real-time sensor telemetry, and arranged buttons for manual and automated missions.	app.py (Flask), index.html, style.css
Kinematics & Autonomy	Logic for precise odometry (using fused IMU/Encoder data) and executing turn-then-drive autonomous sequences.	kinematics.py, automation_controller.py
Sensor Fusion	Processing data from the IMU and wheel encoders to calculate the rover's 2D pose (X, Y, θ) and monitor Roll/Pitch.	imu.py, encoders.py, hardware.py
Computer Vision	System for real-time video streaming, camera servo control, and OpenCV detection of mission-critical QR codes.	qr.py, camera_scan_controller.py, servo_cam.py
System Interface	Handles the essential communication (Serial/I2C) and system health checks.	serial_comm.py, heartbeat.py

🛠️ Setup and Installation

Prerequisites

To run the rover code, you will need the following dependencies and hardware setup:

    Raspberry Pi (preferably Pi 4/5) with SSH enabled.

    Python 3 environment.

    Required physical hardware (motors, IMU, encoders, camera, servo).

Getting Started

    Clone the Repository:
    Bash

git clone [YOUR_REPO_URL_HERE]
cd MANN-E_Rover

Install Python Dependencies:
Bash

# Run this command on your Raspberry Pi
pip3 install flask opencv-python-headless RPi.GPIO smbus

(Note: A formal requirements.txt is recommended for future development.)

Run the Flask Server:
Bash

    # This launches the web control dashboard
    python3 app.py

    Access the control interface from your laptop's browser: http://<your_pi_ip_address>:5000

💡 Development Milestones

The following is an overview of the key development steps and their corresponding files, as tracked in the project's commit history:
File	Commit Message	Highlighted Feature
app.py, camera_scan_controller.py, servo_cam.py, qr_1.jpg, qrs.html	Auto camera tilt for scan	Implemented full camera control for autonomous scanning.
automation_controller.py	Automation works first time	Successful end-to-end execution of the primary autonomous mission path.
kinematics.py	Automation Code Complete with OOP, - Still needs fix in working	Refactored movement logic into an Object-Oriented Kinematics model.
encoders.py, imu.py, hardware.py	Absolute distance + Roll, Pitch	Integrated IMU data for calculating 3-axis orientation and refined distance calculation.
data/, .gitignore, camera_feed.py, serial_comm.py, style.css, index.html	initial commit pi	Established basic project structure, web components, and serial communication.
hardware.py, imu.py	July 11th / Functional rover without automation	Stable manual control established and robust sensor reading validation.

🖼️ Media & External Links

    Watch the Sand Testing: See the rover in action at the Airbus testing facility!

    Documentation: [Link to your project documentation (if applicable)]

🤝 Contribution and Contact

For questions or collaboration, please open an issue in this repository.

    Project Lead: [Your Name/Team Lead Name]

    Contribute: Feel free to fork the repository and submit a pull request!
