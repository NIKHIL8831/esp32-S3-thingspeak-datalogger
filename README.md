# esp32-S3-thingspeak-datalogger
This project uses the ESP32 S3 board to generate random analog values (0–1023) and send them to the ThingSpeak server over Wi-Fi every 15 seconds. The data is visualized on a time-series graph on the ThingSpeak dashboard. This simulates sensor data logging without using any physical analog sensor.
#  ESP32 Random Data Logger to ThingSpeak

This project uses an **ESP32 board** to simulate analog sensor data by generating random values between 0 and 1023. These values are sent every 8 seconds to a **ThingSpeak server** using Wi-Fi, where they are displayed on a time-series graph.

##  Features

- ESP32 connects to Wi-Fi
- Generates random analog values (simulating sensor input)
- Sends data to ThingSpeak using HTTP protocol
- Visualizes data on the ThingSpeak dashboard

##  Requirements

- ESP32 S3 (any variant, e.g., ESP32-S3)
- Arduino IDE with:
  - WiFi.h
  - HTTPClient.h libraries
- ThingSpeak account (free)
- Internet-connected Wi-Fi hotspot/router

##  ThingSpeak Setup
1. Go to [ThingSpeak.com](https://thingspeak.com/)
2. Sign in and create a New Channel
3. Enable Field 1 for data
4. Save the channel and note your Write API Key
5. Copy the API key and paste it into the code

##  How It Works
The ESP32 connects to Wi-Fi, generates a new random number every 15 seconds, and sends it to ThingSpeak in this format

