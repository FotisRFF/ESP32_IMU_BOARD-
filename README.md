# ESP32-C3-BNO055-MOCAP

An open-source, ultra-compact wireless motion-capture node engineered for wearable full-body motion tracking. Built around the **ESP32-C3 Mini** and **Bosch BNO055 9-axis IMU**, this 35 × 35 mm platform is designed for multi-node operation using low-latency **ESP-NOW** communication.

---

## Key Hardware Features

- **Core Processing:** Powered by the **ESP32-C3 Mini**, featuring a 32-bit RISC-V single-core processor running at up to 160 MHz with integrated 2.4 GHz wireless connectivity.

- **9-Axis Motion Sensing:** Onboard **Bosch BNO055** 9-DOF IMU combining a 3-axis accelerometer, 3-axis gyroscope, and 3-axis magnetometer with integrated sensor-fusion processing.

- **Absolute Orientation:** The BNO055 provides fused orientation data including **quaternions and Euler angles**, allowing each node to determine its orientation in space.

- **Wireless Communication:** **ESP-NOW peer-to-peer networking** enables multiple wearable nodes to communicate directly with a central receiver without requiring a conventional Wi-Fi router or access point.

- **LiPo Power Management:** Integrated **1S LiPo battery charging and power management**, supporting a 3.7 V nominal / 4.2 V fully charged single-cell battery.

- **Wearable Form Factor:** Ultra-compact **35 × 35 mm 4-layer PCB** designed for mounting on body straps and wearable platforms.

- **Peripherals & Debugging:** USB Type-C connectivity for programming, debugging, and power, alongside exposed GPIOs and onboard diagnostic LEDs.

---

## Full-Body Motion Capture Architecture

The system is designed around multiple wearable sensor nodes communicating with a central receiver through ESP-NOW.

<pre>
 ┌─────────────┐
 │  Head Node  │
 └──────┬──────┘
        │
        │ ESP-NOW
        ▼
 ┌───────────────────────┐
 │                       │
 │  Central Hub / Master │ ────────> PC / Host Software
 │    (Receiver Node)    │
 │                       │
 └───────────▲───────────┘
             │
             │ ESP-NOW
      ┌──────┴───────┐
      │              │
 ┌────┴────┐    ┌────┴────┐
 │  Torso  │    │ Arm /   │
 │  Node   │    │ Leg     │
 └─────────┘    │ Nodes   │
                │ (5–10)  │
                └─────────┘
</pre>

---

## PCB Layer Architecture

Designed in **Altium Designer**, the 4-layer PCB features a compact high-density layout optimized for clean power distribution and reliable signal return paths.

| Layer | Designation | Description |
| :--- | :--- | :--- |
| **L1** | `SIG` | Primary Component Placement & Top Signal Routing |
| **L2** | `GND` | Solid Internal Ground Plane |
| **L3** | `PWR` | Dedicated Internal Power Distribution Plane |
| **L4** | `SIG + GND` | Bottom Signal Routing & Secondary Ground Pour |

### Layer Previews

<details>
<summary><b>Click to expand layer views</b></summary>

### L1 — Signal

<img width="100%" alt="L1 SIG" src="https://github.com/user-attachments/assets/b8c8f218-e328-44df-8001-f4d3a7ccfeab" />

### L2 — Ground

<img width="100%" alt="L2 GND" src="https://github.com/user-attachments/assets/e4a734b8-dea2-48d9-a056-546f5d2985f7" />

### L3 — Power

<img width="100%" alt="L3 PWR" src="https://github.com/user-attachments/assets/49537f79-96bf-4cfc-a1e3-ba3ef9e25abb" />

### L4 — Signal + Ground

<img width="100%" alt="L4 SIG + GND" src="https://github.com/user-attachments/assets/e3f815d3-db63-4863-9e2a-76b76b9e1210" />

</details>

---

## 3D PCB Rendering

<p align="center">
  <img width="100%" alt="3D View" src="https://github.com/user-attachments/assets/591966c6-bb13-4303-9dbd-e98803343782" />
</p>

---

## Power Architecture

The node is designed around a single-cell LiPo battery with integrated charging and power management.

<pre>
        USB Type-C
             │
             ▼
     ┌───────────────┐
     │  LiPo Charger │
     └───────┬───────┘
             │
             ▼
       ┌───────────┐
       │  1S LiPo  │
       │  3.7 / 4.2V
       └─────┬─────┘
             │
             ▼
     ┌───────────────┐
     │ Power System  │
     └───────┬───────┘
             │
       ┌─────┴─────┐
       │           │
       ▼           ▼
 ┌──────────┐ ┌──────────┐
 │ ESP32-C3 │ │  BNO055  │
 └──────────┘ └──────────┘
</pre>

---

## Repository Structure

<pre>
├── Altium/               # Schematic & PCB layout project files
├── Firmware/             # ESP32-C3 source code and ESP-NOW implementation
├── Fabrication/          # Gerber files, BOM, and manufacturing data
├── Documentation/        # Hardware documentation and project images
└── README.md             # Project documentation
</pre>

---

## Applications

The platform is intended for applications such as:

- Full-body motion capture
- Biomechanical analysis
- Wearable robotics
- Human movement tracking
- Gesture recognition
- VR / AR interaction
- Sports motion analysis
- Robotics and humanoid control

---

## Project Status

**Status:** In Development

Current development focuses on PCB validation, BNO055 integration, ESP-NOW multi-node communication, and real-time motion-data acquisition.

---

## Project Preview

<p align="center">
  <img width="100%" alt="ESP32-C3 BNO055 MoCap Node" src="https://github.com/user-attachments/assets/591966c6-bb13-4303-9dbd-e98803343782" />
</p>
