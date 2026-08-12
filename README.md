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

<img width="100%" alt="L1 SIG" src="<img width="3440" height="1392" alt="image" src="https://github.com/user-attachments/assets/f1fb24e9-21bb-44eb-9787-6a526ece71a8" />
" />

### L2 — Ground

<img width="100%" alt="L2 GND" src="<img width="3440" height="1392" alt="image" src="https://github.com/user-attachments/assets/1471e5b8-fee8-45dd-87a0-2817e8b1c78b" />
" />

### L3 — Power

<img width="100%" alt="L3 PWR" src="<img width="3440" height="1392" alt="image" src="https://github.com/user-attachments/assets/80c487e6-1b53-4f0f-a7c1-ed7469ed197c" />
" />

### L4 — Signal + Ground

<img width="100%" alt="L4 SIG + GND" src="<img width="3440" height="1392" alt="image" src="https://github.com/user-attachments/assets/36fb90a5-a4fa-4f02-b61a-fd2b047c8923" />
" />

</details>

---

## 3D PCB Rendering

<p align="center">
  <img width="100%" alt="3D View" src="<img width="3440" height="1392" alt="image" src="<img width="3440" height="1392" alt="image" src="https://github.com/user-attachments/assets/d8f89d56-4916-4111-9fb2-4058a8d6f97f" />
" />
" />
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


