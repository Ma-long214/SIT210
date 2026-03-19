# SIT210

# Task 2.1P: Sending Temperature and Light Data to the Web

## System Overview
This project monitors environmental conditions (Temperature and Light level) in Linda's home and sends the data to the ThingSpeak cloud platform. It uses an Arduino Nano 33 IoT connected to a DHT11 sensor and a BH1750 digital light sensor.

## Hardware Components
- **Arduino Nano 33 IoT**: Main microcontroller with WiFi connectivity.
- **DHT11 Sensor**: Measures ambient temperature.
- **BH1750 Sensor (5-pin)**: Measures light intensity in Lux via I2C.
- **ThingSpeak**: Cloud IoT platform for data visualization.

## Code Structure (Modular Approach)
The program is divided into functional modules to ensure clarity and maintainability:

1. **Setup & Initialization**:
   Starts Serial communication, I2C bus (`Wire.begin`), and initializes both sensors.
   
2. **`connectToWiFi()`**:
   Handles the WiFi connection process, including retries if the connection is lost.

3. **`readSensors()`**:
   Collects data from the DHT11 (Digital) and BH1750 (I2C) sensors and stores them in global variables.

4. **`sendDataToThingSpeak()`**:
   Maps the sensor data to ThingSpeak fields and performs an HTTP POST request to update the cloud channel.

## ThingSpeak Channel
The data is visualized in real-time on ThingSpeak:
- **Field 1**: Temperature (°C)
- **Field 2**: Light Intensity (Lux)
