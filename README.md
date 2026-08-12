# ESP32-C3-BNO055-MOCAP

An open-source, ultra-compact wireless motion-capture node engineered for wearable full-body motion tracking. Built around the **ESP32-C3 Mini** and **Bosch BNO055 9-axis IMU**, this 35 × 35 mm platform is designed for multi-node operation using low-latency **ESP-NOW** communication.

---

## Key Hardware Features

* **Core Processing:** Powered by the **ESP32-C3 Mini**, featuring a 32-bit RISC-V single-core processor running at up to 160 MHz with integrated 2.4 GHz wireless connectivity.

* **9-Axis Motion Sensing:** Onboard **Bosch BNO055** 9-DOF IMU combining a 3-axis accelerometer, 3-axis gyroscope, and 3-axis magnetometer with integrated sensor-fusion processing.

* **Absolute Orientation:** The BNO055 provides fused orientation data including **quaternions and Euler angles**, allowing each node to independently determine its orientation in space.

* **Wireless Communication:** **ESP-NOW peer-to-peer networking** enables multiple wearable nodes to communicate directly with a central receiver without requiring a conventional Wi-Fi router or access point.

* **LiPo Power Management:** Integrated **1S LiPo battery charging and power management**, supporting a 3.7 V nominal / 4.2 V fully charged single-cell battery for completely untethered operation.

* **Wearable Form Factor:** Ultra-compact **35 × 35 mm 4-layer PCB** designed for mounting on body straps and wearable platforms with minimal interference to natural movement.

* **Peripherals & Debugging:** USB Type-C connectivity for programming, debugging, and power, alongside exposed GPIOs and onboard diagnostic LEDs.

---

## Full-Body Motion Capture Architecture

The system is designed around multiple wearable sensor nodes communicating with a central receiver through ESP-NOW.

```text
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


| Layer  | Designation | Description                                      |
| :----- | :---------- | :----------------------------------------------- |
| **L1** | `SIG`       | Primary Component Placement & Top Signal Routing |
| **L2** | `GND`       | Solid Internal Ground Plane                      |
| **L3** | `PWR`       | Dedicated Internal Power Distribution Plane      |
| **L4** | `SIG + GND` | Bottom Signal Routing & Secondary Ground Pour    |
