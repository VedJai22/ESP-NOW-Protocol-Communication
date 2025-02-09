# ESP-NOW-Protocol-Communication
"ESP32 communication using ESP-NOW protocol"
Step-by-Step Guide for ESP-NOW Protocol
### Components Required

To set up ESP-NOW communication between two ESP32 devices, you will need the following components:

- **2 x ESP32 Development Boards** (e.g., ESP32 DevKit, NodeMCU-ESP32)
- **USB cables** for power and programming the ESP32 boards
- **Arduino IDE** with ESP32 board support installed
- **Computer** for programming and serial monitoring

### Steps to Establish ESP-NOW Communication

#### 1. Set Up Arduino IDE for ESP32
1. Install the ESP32 board package in Arduino IDE:
   - Go to `File > Preferences` and add this URL to the **Additional Boards Manager URLs**:
     ```
     https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json
     ```
   - Go to `Tools > Board > Boards Manager`, search for **ESP32**, and install the package.
   - Select the ESP32 board: `Tools > Board > ESP32 Dev Module`.

#### 2. Install ESP-NOW Library
- ESP-NOW is built into the ESP32 Arduino core, so no additional library is required.

#### 3. Upload Transmitter Code
1. Connect the first ESP32 to your computer.
2. Open the `transmitter.ino` sketch in Arduino IDE.
3. Replace the `receiverAddress` with the MAC address of the receiver ESP32.
4. Upload the code to the transmitter ESP32.

#### 4. Upload Receiver Code
1. Connect the second ESP32 to your computer.
2. Open the `receiver.ino` sketch in Arduino IDE.
3. Upload the code to the receiver ESP32.

#### 5. Get MAC Address of Receiver
- If you don’t know the MAC address of the receiver ESP32, upload the following code to it and check the Serial Monitor:
  ```cpp
  #include <WiFi.h>
  void setup() {
    Serial.begin(115200);
    WiFi.mode(WIFI_MODE_STA);
    Serial.println(WiFi.macAddress());
  }
  void loop() {}

---
