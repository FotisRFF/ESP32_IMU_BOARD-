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
 ├─────────────┤                      │  (Receiver Node)      │     (3D Avatar / MoCap)
 │ Arm / Leg   │ ───────────────────> │                       │
 │ Nodes (5-10)│                      │                       │
 └─────────────┘                      └───────────────────────┘
