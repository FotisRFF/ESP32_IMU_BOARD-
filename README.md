readme_content = """# ESP32-C3 Mini BNO055 MoCap Node

An open-source, ultra-compact (35 x 35 mm) wireless motion-capture (MoCap) node designed for body-worn biomechanical tracking. Engineered to operate in multi-node clusters (5 to 10 boards strapped across a human body), the platform utilizes **ESP-NOW peer-to-peer networking** for low-latency, router-less data synchronization alongside an onboard **Bosch BNO055 9-axis sensor** and **1S LiPo battery charger**.

---

## Key Hardware & System Features

* **ESP-NOW Peer-to-Peer Networking:** Designed for multi-node setups where 5 to 10 boards communicate directly over low-latency, peer-to-peer ESP-NOW protocol—transmitting real-time orientation data without requiring a Wi-Fi access point or router.
* **9-Axis Absolute Orientation Sensing:** Onboard **Bosch BNO055** smart 9-DOF IMU (accelerometer, gyroscope, and magnetometer) running hardware sensor fusion to directly output absolute quaternions and Euler angles for accurate limb tracking.
* **1S LiPo Charging & Battery Management:** Integrated single-cell (1S 3.7V / 4.2V peak) LiPo charger with automated power-path management, allowing completely untethered, wireless operation when strapped to the body.
* **Wearable Form Factor:** Ultra-compact 35 x 35 mm 4-layer PCB tailored for mounting on body straps (limbs, torso, head) without restricting natural human movement.
* **Core Processing:** Powered by the **ESP32-C3 Mini** (RISC-V 32-bit single-core CPU up to 160 MHz) with onboard 2.4 GHz antenna.
* **Peripherals & I/O:** USB Type-C interface for programming, debugging, and charging, plus exposed GPIOs and diagnostic status LEDs.

---

## Full-Body Tracking Architecture

```text
 ┌─────────────┐    ESP-NOW (P2P)     ┌───────────────────────┐
 │ Head Node   │ ───────────────────> │                       │
 ├─────────────┤                      │                       │
 │ Torso Node  │ ───────────────────> │  Central Hub / Master │ ──> PC / Host Software
 ├─────────────┤                      │  (Receiver Node)      │     
 │ Arm / Leg   │ ───────────────────> │                       │
 │ Nodes (5-10)│                      │                       │
 └─────────────┘                      └───────────────────────┘
### Layer Previews

<details>
<summary><b>Click to expand layer views</b></summary>

* **L1 (SIG):**  
  <img width="100%" alt="L1 SIG" src="https://github.com/user-attachments/assets/b8c8f218-e328-44df-8001-f4d3a7ccfeab" />

* **L2 (GND):**  
  <img width="100%" alt="L2 GND" src="https://github.com/user-attachments/assets/e4a734b8-dea2-48d9-a056-546f5d2985f7" />

* **L3 (PWR):**  
  <img width="100%" alt="L3 PWR" src="https://github.com/user-attachments/assets/49537f79-96bf-4cfc-a1e3-ba3ef9e25abb" />

* **L4 (SIG + GND):**  
  <img width="100%" alt="L4 SIG+GND" src="https://github.com/user-attachments/assets/e3f815d3-db63-4863-9e2a-76b76b9e1210" />

</details>

---

## 3D PCB Rendering

<p align="center">
  <img width="100%" alt="3D View" src="https://github.com/user-attachments/assets/591966c6-bb13-4303-9dbd-e98803343782" />
</p>

---

## Repository Structure
