# ESP32-S3 Face Recognition Codebase

This repository contains the code and setup instructions for integrating the **Seeed Studio XIAO ESP32S3 Sense** with a **face recognition AI model**.  
The project is based on the [Instructables tutorial by Limengdu](https://www.instructables.com/Face-Recognition-Based-Attendance-System-Using-XIA/) and serves as a foundation for experimenting with **edge AI and computer vision** on the ESP32 platform.

---

## 🚀 Project Overview

The goal of this project is to:
- Capture images using the onboard ESP32-S3 camera.  
- Perform **face detection and recognition** using an AI model running locally or through a connected service.  
- Explore real-time inference on low-power edge devices.

This repo currently focuses on setting up the camera and running the base face recognition system. Future updates will include custom model integration and cloud sync.

---

## 🧠 Hardware Requirements

- **Seeed Studio XIAO ESP32S3 Sense** (or compatible ESP32-S3 board)  
- **Camera Module** (OV2640)  
- **USB-C cable**  
- **MicroSD card** *(optional, for image logging)*

---

## 💻 Software Requirements

- **Arduino IDE** (latest version)  
- **ESP32 board package** installed  
- Libraries used:
  - `esp_camera.h`
  - `WiFi.h`
  - (optional) `FS.h` / `SD_MMC.h` if saving to SD card

---

## ⚙️ Setup Instructions

1. **Install ESP32 Support in Arduino IDE**
   - Go to **File → Preferences** and add this URL to *Additional Board Manager URLs*:  
     ```
     https://dl.espressif.com/dl/package_esp32_index.json
     ```
   - Then go to **Tools → Board → Boards Manager** and search for **ESP32**.

2. **Select Your Board**
   - Choose: `Seeed XIAO ESP32S3` (or equivalent).
   - Set proper **COM port** and **Upload Speed** (usually 921600).

3. **Configure the Camera Pins**
   - Pin definitions are included in `board_config.h` (based on the Instructables setup).

4. **Upload the Code**
   - Open the `.ino` sketch and update your Wi-Fi credentials:
     ```cpp
     const char* ssid = "YOUR_WIFI_SSID";
     const char* password = "YOUR_WIFI_PASSWORD";
     ```
   - Compile and upload the sketch to your board.

5. **Access the Web Server**
   - After upload, open the **Serial Monitor** at `115200 baud`.
   - Note the IP address printed in the terminal.
   - Visit that IP address in your browser to see the live camera feed and face recognition interface.

---

## 🧩 Repository Structure

