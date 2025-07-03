
# 🤖 ESP32-Based 4 DOF Robot Arm Controlled via Smartphone using WebSocket

---

## 🔍 **Project Overview**
This project implements a **4 Degrees-of-Freedom (DOF) robotic arm** that is controlled wirelessly using a smartphone or computer browser. The ESP32 microcontroller acts as a Wi-Fi Access Point (SoftAP) and hosts a web page that users can access to control the robotic arm's movements in real-time using **WebSockets**.

---

## 🔧 **Technologies & Components Used**

### 🔌 Hardware:
- **ESP32 NodeMCU Development Board**
- **4 × SG90 Servo Motors** (for Base, Shoulder, Elbow, and Gripper)
- Breadboard, Jumper Wires, and Acrylic/Wooden Frame for structure
- 5V Battery Pack or DC Supply for external servo power

### 🔊 Software & Protocols:
- **Arduino IDE** for programming ESP32
- **ESPAsyncWebServer Library** (Web Server & WebSocket)
- **ESP32Servo Library** to control servos
- **AsyncTCP & AsyncWebSocket Libraries** for efficient WebSocket communication
- **HTML, CSS, JavaScript** for web-based control panel
- Wi-Fi SoftAP mode on ESP32 for creating a local Wi-Fi hotspot

---

## 🏙️ **Circuit Diagram & Wiring**

| Servo    | ESP32 Pin |
|------    |-----------|
| Base     | GPIO 12   |
| Shoulder | GPIO 14   |
| Elbow    | GPIO 27   |
| Gripper  | GPIO 26   |

- Servo VCC: External 5V battery pack recommended for stable operation.
- Servo GND: Common ground with ESP32.

---

## 🔑 **Key Features**
- ESP32 creates its own Wi-Fi hotspot (SoftAP mode)
- Hosted web interface served by ESP32
- Real-time **WebSocket-based** control
- Control **4 servos** independently
- **Recording and Playback:** Record servo movements and replay them

---

## 🔬 **How It Works**

1. ESP32 initializes as a SoftAP.
2. Hosts a web page accessible via smartphone/laptop.
3. User interacts with the web UI using sliders & buttons.
4. JavaScript sends commands to ESP32 using WebSocket.
5. ESP32 receives and parses these commands to adjust servo angles.
6. Movement commands can be recorded and replayed in a loop.

---

## 🔢 **Setup Instructions**

### ✅ 1. Flashing the ESP32:
- Install **Arduino IDE** and ESP32 board support.
- Install the following libraries in Arduino IDE:
  - [ESP32 board URL](https://dl.espressif.com/dl/package_esp32_index.json)
  - [ESPAsyncWebServer](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqa2NfRFE1RGs2ajFOVFZMazVTWllHN0dVYkVMd3xBQ3Jtc0ttNlUxMjFWRWxuS2JqYTJBNVo2V2E3U1Q4alFaYmRYRGpYWXdZaWxxSDFmbUtwc2d5c0NZT25fa1dLUXFLem0yQVoyLVNKSEMzcXYwSkVqTU0wTktkdFhmVXFIY1RFZHJCc25FLU43c200ekFrOHRLZw&q=https%3A%2F%2Fgithub.com%2Fme-no-dev%2FESPAsyncWebServer%2Farchive%2Frefs%2Fheads%2Fmaster.zip&v=cVSvg6VQhGU)
  - [AsyncTCP Library](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbnZaYzlDa2xGbGVYYTF3em9rYWI4Tk9OZFVxUXxBQ3Jtc0tuSGJneEo2VTRBQ0lETHR0UmhfdE5vU2lvZWNjVDcyTGRhZUZhX3ZPUGxzUWh4bnJJTF83MzBGN053SEUxTlpYaGVub3JnTlNmTC16YnQyaDVJNHhOSnZaZjZMWG1BNUczSFRZa1IwVDdxYVBURWFnbw&q=https%3A%2F%2Fgithub.com%2Fme-no-dev%2FAsyncTCP%2Farchive%2Frefs%2Fheads%2Fmaster.zip&v=cVSvg6VQhGU)
  

- Upload the Arduino sketch (`robotic_arm.ino`).

### ✅ 2. Connecting the Hardware:
- Wire the servos to ESP32 as per the diagram
- Power the ESP32 via USB.
- Use a separate 5V power supply for the servos.

### ✅ 3. Connecting to the ESP32 Network:
- On your phone/computer, connect to the Wi-Fi network:
  - **SSID:** `RobotArm-AP`
  - **Password:** `12345678`
- Open browser and go to: `192.168.4.1`

### ✅ 4. Using the Web Interface:
- Use sliders/buttons to control each servo.
- Press **Record** to save a movement sequence.
- Press **Play** to replay the recorded movements.

---

## 📊 **Results & Observations**

- Real-time movement control with minimal latency.
- Smooth servo response due to optimized non-blocking WebSocket communication.
- Ability to record and replay complex motion sequences.
- Stable performance within ~20-30 meter Wi-Fi range.

---

## 📊 **Challenges Faced**

| Challenge                                    | Solution                                                          |
|--------------------------------------------- | ----------------------------------------------------------------- |
| Servo jitter due to insufficient power       | Used external 5V battery pack                                     |
| IP address changes after each reboot         | 	Configured static IP or used mDNS for easier network access      |
| Cross-browser compatibility of web interface | Tested and optimized the web UI across Chrome, Firefox, and Edge  |

---

## 🔄 **Future Scope**

- ✨ Upgrade communication to **MQTT** for cloud control.
- ✨ Add RESTful API endpoints for more versatile control.
- ✨ Build a mobile app (Flutter/React Native) for intuitive control.
- ✨ Integrate sensors (e.g., distance sensor, camera) for automation.

---

## 🔗 **Repository Structure**

```
ESP32-Robot-Arm-Control/
├── src/
│   └── robot_arm_control.ino
├── docs/
│   ├── Robot Arm diagram.png
│   └── development_process.jpg
│   └── mobileapp_view.jpg
│   └── photo.jpg
│
└── README.md
```


