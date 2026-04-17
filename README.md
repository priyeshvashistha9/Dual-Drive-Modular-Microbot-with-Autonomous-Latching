# Design and Implementation of a Dual-Drive Modular Microbot

This project details the iterative design and validation of a modular microbotic unit capable of autonomous magnetic detection and mechanical latching. Originally inspired by the "Microbots" from *Big Hero 6*, this platform serves as a foundation for research into programmable matter and modular swarm robotics.

---

## 🚀 Project Overview
The project evolved from a wireless architecture to a **tethered validation platform** to overcome thermal and spatial constraints encountered during prototyping. This shift allowed for the successful verification of the unit's kinetic mobility and its ability to form rigid physical bonds with adjacent units.

### Key Features
* **Dual-Drive Kinematics**: Utilizes dual continuous rotation servos for spatial navigation.
* **Two-Stage Docking**: Employs passive magnetic alignment for initial contact and active solenoid-driven latching for rigid structural integrity.
* **Autonomous Sensing**: Features A3144 Hall Effect sensors for localized magnetic field detection to trigger automated latching.
* **Web Serial Interface**: A custom browser-based control interface that establishes a low-latency link via the Web Serial API.

---

## 🛠 Hardware Architecture
The system utilizes a segregated power plant to isolate high-current mechanical "muscles" from sensitive logic components.

* **Logic Tier**: Arduino UNO R3 (5V) tethered via USB.
* **Power Tier**: 7.4V Li-Po battery dedicated to electromechanical components.
* **Isolation**: A **DRV8833 Dual H-Bridge** motor driver routes high-current power to solenoids while protecting the microcontroller from inductive kickback.
* **Regulation**: A **UBEC (Buck Converter)** steps down 7.4V to a stable 5V rail exclusively for the servos to prevent system resets.

---

## 💻 Software Logic & Failsafes
The firmware is designed as a continuous state machine to ensure safe and efficient operation.

* **Hold-to-Move Logic**: Maps keyboard inputs (W, A, S, D) to directional movement; servos halt immediately upon key release to prevent runaway motion.
* **Edge-Triggered Actuation**: The autonomous docking routine only fires the solenoid for a 1.5-second window upon detecting a state change.
* **Power Optimization**: The latch is "normally closed" via a mechanical spring, meaning the solenoids only draw current during transitional phases.

---

## 📈 Results and Failure Analysis
* **Wireless Limitations**: Initial testing with the Arduino Nano 33 IoT (3.3V) failed due to electromagnetic interference and thermal runaway within the unventilated 3D-printed chassis.
* **Validation Success**: The tethered platform successfully validated the hardware's ability to execute rapid, rigid mechanical connections required for self-reconfigurable systems.

---

## 🎓 Author
**Priyesh Vashistha**
Dept. of Electrical and Computer Engineering
Queen's University, Kingston, Ontario, Canada
Student ID: 20479905

---

