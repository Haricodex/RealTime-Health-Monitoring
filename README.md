# RealTime-Health-Monitoring
"An ESP32-based IoT Biomedical Monitoring System that tracks heart rate, SpO2, body temperature, and humidity. Data is sent to the Blynk IoT app over Wi-Fi for real-time monitoring. Uses sensors like MAX30100, DS18B20, and DHT11 for accurate health tracking."

# **ESP32 Biomedical Monitoring System**

## **1. Project Overview**
The **ESP32 Biomedical Monitoring System** is an IoT-based health tracking solution that continuously monitors vital signs such as **heart rate, SpO2, body temperature, and humidity**. The system integrates **ESP32**, **Blynk IoT**, and various biomedical sensors to provide real-time health monitoring. The data is transmitted over Wi-Fi and visualized using the **Blynk mobile app**.

## **2. System Architecture**
This system consists of **hardware components** (ESP32 and sensors) and **software components** (Blynk IoT platform and Arduino IDE). It enables **remote monitoring**, providing real-time insights into a patient's health.

### **2.1 Software & Tools Used**
#### **Blynk IoT Platform**
- **Software Type:** Cloud-based IoT platform
- **Functionality:** Allows real-time monitoring and visualization of sensor data.
- **Integration:** ESP32 communicates with Blynk using virtual pins over Wi-Fi.
- **Graphical Display:** Sensor data is displayed in real-time using widgets like:
  - **Graph Widgets** – For continuous tracking of heart rate and SpO2.
  - **Gauge Widgets** – For temperature and humidity visualization.
  - **Notification Alerts** – Sends alerts if values exceed thresholds.

#### **Arduino IDE**
- **Software Type:** Open-source development environment
- **Functionality:** Used to write, compile, and upload the ESP32 firmware.
- **Integration:** Supports ESP32 libraries and serial monitoring for debugging.

## **3. Features of the System**
- **Continuous Monitoring** – Real-time tracking of vital signs.
- **Cloud Integration** – Stores and displays data on the Blynk Cloud.
- **Graphical Visualization** – Displays data using interactive graphs and gauges.
- **Event-Driven Alerts** – Sends notifications for abnormal readings.
- **Remote Accessibility** – View sensor data from anywhere using the Blynk app.

## **4. System Requirements**
### **4.1 Hardware Components**
- **ESP32 Microcontroller** – Manages sensor readings and data transmission.
- **MAX30100 Pulse Oximeter Sensor** – Measures heart rate and SpO2 levels.
- **DS18B20 Temperature Sensor** – Tracks body temperature.
- **DHT11 Sensor** – Monitors room temperature and humidity.

### **4.2 Software Requirements**
- **Arduino IDE (Version 1.8 or later)**
- **Blynk IoT App (Android/iOS)**
- **ESP32 Board Package**
- **Required Libraries:**
  - `WiFi.h`
  - `BlynkSimpleEsp32.h`
  - `MAX30100_PulseOximeter.h`
  - `OneWire.h`, `DallasTemperature.h`
  - `DHT.h`

## **5. Installation & Setup Guide**
### **5.1 Setting Up Blynk IoT**
1. Install the **Blynk IoT App** (Android/iOS).
2. Create a new project and select **ESP32** as the device.
3. Add the following widgets:
   - **SuperChart** (for tracking heart rate & SpO2 over time)
   - **Gauge** (for temperature and humidity display)
   - **LED Indicator** (for alerts when values exceed thresholds)
4. Obtain the **Blynk Authentication Token** and replace it in the code.

### **5.2 Uploading & Running the Code**
1. Open **Arduino IDE** and paste the ESP32 sketch.
2. Select **ESP32 Dev Module** in **Tools > Board**.
3. Set the **correct COM Port** in **Tools > Port**.
4. Install required libraries (if missing).
5. Click **Upload** and open **Serial Monitor** (baud rate: 115200).
6. Open **Blynk App** and verify real-time data updates.

## **6. API Endpoints & Data Visualization**
### **6.1 Data Visualization in Blynk**
- **Graph-Based Display:**
  - Heart rate and SpO2 are plotted over time using the **SuperChart widget**.
  - Temperature and humidity values are displayed using **Gauges**.
- **Alerts and Notifications:**
  - If the BPM is too high or SpO2 is too low, a **notification alert** is sent.
  - A red LED icon on the dashboard indicates abnormal health conditions.

### **6.2 API Endpoints for IoT Data Transmission**
ESP32 sends data to Blynk using **virtual pins**. Example:
```cpp
Blynk.virtualWrite(V0, temperature);
Blynk.virtualWrite(V1, humidity);
Blynk.virtualWrite(V2, BPM);
Blynk.virtualWrite(V3, SpO2);
```
- **V0:** Temperature Data
- **V1:** Humidity Data
- **V2:** Heart Rate (BPM)
- **V3:** SpO2 Percentage

## **6.3. Future Enhancements**
- **Cloud Data Storage** – Store historical data for long-term analysis.
- **AI-Based Health Predictions** – Use machine learning for anomaly detection.
- **Remote Doctor Alerts** – Notify doctors/caregivers in case of emergencies.

## **7. References**
- **Blynk Documentation:** [https://docs.blynk.io](https://docs.blynk.io)
- **ESP32 Technical Guide:** [https://docs.espressif.com](https://docs.espressif.com)
- **MAX30100 Pulse Oximeter Guide:** [https://lastminuteengineers.com/max30100-pulse-oximeter-arduino-tutorial/](https://lastminuteengineers.com/max30100-pulse-oximeter-arduino-tutorial/)

