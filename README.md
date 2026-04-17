# Dual-Drive-Modular-Microbot-with-Autonomous-Latching
Dual-Drive Modular Microbot, a bio-inspired swarm robotics platform. This project details the design and validation of a single "seed" unit capable of autonomous magnetic detection and high-strength mechanical latching.
# [cite_start]Design and Implementation of a Dual-Drive Modular Microbot [cite: 1]

[cite_start]This project details the iterative design and validation of a modular microbotic unit capable of autonomous magnetic detection and mechanical latching[cite: 8]. [cite_start]Originally inspired by the "Microbots" from *Big Hero 6*, this platform serves as a foundation for research into programmable matter and modular swarm robotics[cite: 8, 13].

---

## 🚀 Project Overview
[cite_start]The project evolved from a wireless architecture to a **tethered validation platform** to overcome thermal and spatial constraints encountered during prototyping[cite: 2, 9]. [cite_start]This shift allowed for the successful verification of the unit's kinetic mobility and its ability to form rigid physical bonds with adjacent units[cite: 11, 148].

### Key Features
* [cite_start]**Dual-Drive Kinematics**: Utilizes dual continuous rotation servos for spatial navigation[cite: 29, 96].
* [cite_start]**Two-Stage Docking**: Employs passive magnetic alignment for initial contact and active solenoid-driven latching for rigid structural integrity[cite: 43, 44, 46].
* [cite_start]**Autonomous Sensing**: Features A3144 Hall Effect sensors for localized magnetic field detection to trigger automated latching[cite: 32, 101].
* [cite_start]**Web Serial Interface**: A custom browser-based control interface that establishes a low-latency link via the Web Serial API[cite: 106, 108].

---

## 🛠 Hardware Architecture
[cite_start]The system utilizes a segregated power plant to isolate high-current mechanical "muscles" from sensitive logic components[cite: 11, 28].

* [cite_start]**Logic Tier**: Arduino UNO R3 (5V) tethered via USB[cite: 30, 38].
* [cite_start]**Power Tier**: 7.4V Li-Po battery dedicated to electromechanical components[cite: 37, 50].
* [cite_start]**Isolation**: A **DRV8833 Dual H-Bridge** motor driver routes high-current power to solenoids while protecting the microcontroller from inductive kickback[cite: 49, 94].
* [cite_start]**Regulation**: A **UBEC (Buck Converter)** steps down 7.4V to a stable 5V rail exclusively for the servos to prevent system resets[cite: 98].

---

## 💻 Software Logic & Failsafes
[cite_start]The firmware is designed as a continuous state machine to ensure safe and efficient operation[cite: 112].

* [cite_start]**Hold-to-Move Logic**: Maps keyboard inputs (W, A, S, D) to directional movement; servos halt immediately upon key release to prevent runaway motion[cite: 114, 118].
* [cite_start]**Edge-Triggered Actuation**: The autonomous docking routine only fires the solenoid for a 1.5-second window upon detecting a state change[cite: 123, 125].
* [cite_start]**Power Optimization**: The latch is "normally closed" via a mechanical spring, meaning the solenoids only draw current during transitional phases[cite: 121, 122].

---

## 📈 Results and Failure Analysis
* [cite_start]**Wireless Limitations**: Initial testing with the Arduino Nano 33 IoT (3.3V) failed due to EMI and thermal runaway within the unventilated 3D-printed chassis[cite: 151, 153].
* [cite_start]**Validation Success**: The tethered platform successfully validated the hardware's ability to execute rapid, rigid mechanical connections required for self-reconfigurable systems[cite: 164].

---

## 🎓 Author
[cite_start]**Priyesh Vashistha** [cite: 4]
[cite_start]Dept. of Electrical and Computer Engineering [cite: 5]
[cite_start]Queen's University, Kingston, Ontario, Canada [cite: 6]
[cite_start]Student ID: 20479905 [cite: 6]

---

## 📚 References
* [cite_start][1] M. Yim et al., "Modular Self-Reconfigurable Robot Systems," 2007[cite: 172].
* [cite_start][2] Arduino UNO R3 & Nano 33 IoT Datasheets[cite: 179, 183].
* [cite_start][3] Texas Instruments, "DRV8833 Dual H-Bridge Motor Driver," 2015[cite: 182].
