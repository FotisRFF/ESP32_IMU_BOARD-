# ESP32-C3 Mini BNO055 9-Axis IMU & 1S LiPo Charger Board

An open-source, ultra-compact (35 x 35 mm) wireless motion-tracking platform featuring the **ESP32-C3 Mini**, an onboard **Bosch BNO055 9-axis Absolute Orientation Sensor**, and integrated **single-cell (1S) LiPo battery management**.

---

## Key Hardware Features

* **Core Processing & Wireless:** Powered by the **ESP32-C3 Mini** (RISC-V 32-bit single-core CPU up to 160 MHz) with integrated 2.4 GHz Wi-Fi and Bluetooth 5 (LE) for real-time telemetry.
* **9-Axis Sensor Fusion:** Features the **Bosch BNO055** smart 9-DOF IMU (3-axis accelerometer, 3-axis gyroscope, and 3-axis magnetometer) with onboard sensor fusion to directly output absolute orientation (Quaternions, Euler angles) and linear acceleration.
* **1S LiPo Charging & Power:** Dedicated onboard single-cell (1S 3.7V / 4.2V peak) LiPo charger circuit with automatic power path management and charging status LED indicators.
* **Ultra-Compact Form Factor:** Dense 35 x 35 mm 4-layer layout optimized for wearables, miniaturized robotics, head-tracking, and compact IoT motion nodes.
* **Power Management:** Efficient onboard 3.3V voltage regulation alongside ESD, overcurrent, and reverse-polarity battery protection.
* **Peripherals & I/O:** USB Type-C interface for programming, debugging, and 1S LiPo battery charging alongside exposed GPIOs for expansion.

---

## PCB Layer Architecture

Designed in **Altium Designer**, the PCB utilizes a dense, optimized 4-layer stack-up to maintain clean power delivery, low noise for analog sensor lines, and solid ground planes for wireless performance:

| Layer | Designation | Description |
| :--- | :--- | :--- |
| **L1** | `SIG` | Top Component Placement & Primary High-Speed Routing |
| **L2** | `GND` | Continuous Internal Ground Plane for RF & Sensor Shielding |
| **L3** | `PWR` | Internal Power Distribution Planes (3.3V / VBAT / VBUS) |
| **L4** | `SIG + GND` | Bottom Routing & Secondary Ground Pour |

### Layer Previews

<details>
<summary><b>Click to expand layer views</b></summary>

* **L1 (SIG):**  
  <img width="100%" alt="L1 SIG" src="PASTE_YOUR_IMAGE_LINK_HERE" />

* **L2 (GND):**  
  <img width="100%" alt="L2 GND" src="PASTE_YOUR_IMAGE_LINK_HERE" />

* **L3 (PWR):**  
  <img width="100%" alt="L3 PWR" src="PASTE_YOUR_IMAGE_LINK_HERE" />

* **L4 (SIG + GND):**  
  <img width="100%" alt="L4 SIG+GND" src="PASTE_YOUR_IMAGE_LINK_HERE" />

</details>

---

## 3D PCB Rendering

<p align="center">
  <img width="100%" alt="3D View" src="PASTE_YOUR_IMAGE_LINK_HERE" />
</p>

---

## Repository Structure

```text
├── Altium/               # Schematic & PCB layout project files
├── Fabrication/          # Gerber files, BOM, and pick-and-place data
├── Firmware/             # ESP-IDF / Arduino code for BNO055 reading and Wi-Fi/BLE transmission
└── README.md             # Project documentation
