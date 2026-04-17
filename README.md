# Smart IoT-Based Patient Health Monitoring System

This project is an ESP32-based IoT patient health monitoring system designed to measure and analyze vital parameters such as heart rate (BPM), blood oxygen levels (SpO2), body temperature, and environmental conditions. The system hosts a web server on ESP32 for real-time monitoring and includes an alert mechanism for abnormal readings.

## Features
- Measure and display room temperature and humidity using the DHT11 sensor.
- Measure and display body temperature using the DS18B20 sensor.
- Measure and display heart rate (BPM) and blood oxygen levels (SpO2) using the MAX30100 Pulse Oximeter.
- Host a web server on the ESP32 to display the collected data in a user-friendly web interface.
- Alert notification for abnormal health parameters

## Improvements Made
- Implemented alert system for abnormal heart rate values
- Optimized WiFi connectivity for stable real-time monitoring
- Improved data readability on web interface

## Hardware Components
- ESP32 Development Board
- DHT11 Temperature and Humidity Sensor
- DS18B20 Temperature Sensor
- MAX30100 Pulse Oximeter
- Breadboard and Jumper Wires
- 4.7kΩ Resistor (for DS18B20)

## Software Required
- Arduino IDE
- ESP32 Board Manager (installed via Arduino IDE)
- Required Libraries:
  - `WiFi.h`
  - `WebServer.h`
  - `Wire.h`
  - `MAX30100_PulseOximeter.h`
  - `OneWire.h`
  - `DallasTemperature.h`
  - `Bonezegei_DHT11.h`
## System Architecture
Sensor Data → ESP32 Processing → WiFi Transmission → Web Server → User Interface

## Circuit Diagram
Connect the sensors to the ESP32 as follows:

| Component            | ESP32 Pin      |
|----------------------|----------------|
| DHT11                | 18             |
| DS18B20              | 5              |
| MAX30100 Pulse Oximeter | I2C (SDA, SCL)|
| 4.7kΩ Resistor       | Between DS18B20 Data and 3.3V |

## Installation and Setup

1. **Clone the Repository:**
   ```sh
   git clone https://github.com/yourusername/ESP32-Patient-Health-Monitoring.git
   cd ESP32-Patient-Health-Monitoring
   ```

2. **Open the Arduino IDE:**
   - Install the ESP32 Board Manager.
   - Install the required libraries mentioned above.

3. **Update Wi-Fi Credentials:**
   - Open the `ESP32-Patient-Health-Monitoring.ino` file.
   - Update the `ssid` and `password` variables with your Wi-Fi network credentials.

4. **Upload the Code to ESP32:**
   - Connect your ESP32 board to your computer.
   - Select the correct board and port from the Arduino IDE.
   - Click on the upload button.

5. **Open the Serial Monitor:**
   - Set the baud rate to 115200.
   - Observe the connection status and IP address assigned to your ESP32.

6. **Access the Web Server:**
   - Open a web browser and enter the IP address displayed on the Serial Monitor.
   - View the real-time patient health monitoring data.

## Code Explanation

The code consists of the following main parts:

- **Library Inclusions and Definitions:**
  - Include necessary libraries for Wi-Fi, web server, and sensors.
  - Define sensor pins and variables to store sensor data.

- **Setup Function:**
  - Initialize serial communication and sensor objects.
  - Connect to Wi-Fi and start the web server.
  - Initialize the pulse oximeter sensor.

- **Loop Function:**
  - Handle client requests and update sensor readings.
  - Read data from sensors and periodically report it to the Serial Monitor.
  - Serve the HTML page with sensor data when a client connects.

- **HTML Page Generation:**
  - Generate an HTML page with embedded sensor data to be displayed in a web browser.
 



## Output & Results

| | |
|--------------------------|--------------------------|
| <img src="https://github.com/user-attachments/assets/1b4ed722-50cd-4f80-826d-e840199dad8b" width="200"> | <img src="https://github.com/user-attachments/assets/6a29e3c7-420b-45a2-9299-045a0f804801" width="300"> |
| <img src="https://github.com/user-attachments/assets/cf5d8a5e-5b88-450e-868a-dd6e73887ad8" width="300"> |


## Contributions

Feel free to fork this repository and contribute by submitting a pull request. Any improvements, bug fixes, or enhancements are welcome.

## Acknowledgments

- This project was developed by integrating multiple embedded systems concepts and IoT technologies, inspired by standard healthcare monitoring solutions.
