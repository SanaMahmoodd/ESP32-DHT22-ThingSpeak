# ESP32 DHT22 Temperature & Humidity Monitoring with ThingSpeak

An IoT homework project that uses an **ESP32** and a **DHT22 sensor** to monitor temperature and humidity. The ESP32 connects to Wi-Fi and sends both measurements to **ThingSpeak every 20 seconds**, where they appear as public, time-based charts.

## Student Information

- **Name:** Sana Saleh
- **University ID:** 12217400
- **Project:** ESP32 to ThingSpeak (IoT LAB #1)

## Live Project Links

- **ThingSpeak public channel:** https://thingspeak.com/channels/3550005
- **ThingSpeak channel ID:** `3550005`
- **Wokwi simulation:** https://wokwi.com/projects/478881694563573761

## Project Features

- Reads temperature in degrees Celsius (`°C`) and relative humidity (`%`) using the DHT22.
- Connects to the `Wokwi-GUEST` Wi-Fi network in the simulator.
- Sends temperature to **Field 1** and humidity to **Field 2** on ThingSpeak.
- Updates the cloud readings every **20 seconds**.
- Prints sensor readings, the university ID, and upload status to the Serial Monitor.
- Turns on an LED when the temperature is **above 30°C**.

## Components

- ESP32 development board
- DHT22 temperature and humidity sensor
- LED and current-limiting resistor
- Breadboard and jumper wires
- Wokwi simulator
- ThingSpeak IoT platform

## Circuit Connections

| Component | ESP32 connection | Purpose |
| --- | --- | --- |
| DHT22 VCC (+) | 3.3V | Sensor power |
| DHT22 DATA | GPIO 15 | Temperature and humidity data |
| DHT22 GND (-) | GND | Ground |
| LED | GPIO 23, in series with a resistor | Temperature indicator |

See `diagram.json` and the Wokwi simulation for the complete circuit layout and LED ground connection.

## How It Works

1. The DHT22 measures temperature and humidity.
2. The ESP32 reads the measurements through GPIO 15.
3. The ESP32 connects to Wi-Fi.
4. The code sets ThingSpeak **Field 1** to temperature and **Field 2** to humidity.
5. The readings are uploaded to the ThingSpeak channel every 20 seconds.
6. ThingSpeak shows the readings on two public charts with a timeline.
7. If the temperature exceeds 30°C, the LED turns on; otherwise, it turns off.

## Files

| File | Description |
| --- | --- |
| `sketch.ino` | Arduino code for the ESP32 |
| `diagram.json` | Wokwi circuit diagram |
| `libraries.txt` | Libraries used by the Wokwi simulation |
| `README.md` | Project description and instructions |

Screenshots of the **Wokwi circuit**, **ThingSpeak graphs**, and **successful Serial Monitor output** are also used to document the result.
<img width="1455" height="225" alt="image" src="https://github.com/user-attachments/assets/19c94533-de3d-42cd-8d65-abd48283c857" />
<img width="1482" height="621" alt="image" src="https://github.com/user-attachments/assets/de6c9205-7296-4c68-9cc0-a5308dbdfdd3" />
<img width="924" height="830" alt="image" src="https://github.com/user-attachments/assets/e51ef846-3544-481f-bda0-83c8b9c39968" />
<img width="771" height="768" alt="image" src="https://github.com/user-attachments/assets/fa2a45a5-b0b7-4aa3-bd8d-698b98af7752" />
<img width="931" height="858" alt="image" src="https://github.com/user-attachments/assets/e48020a8-c7f0-4f32-bfbd-e73e95b2c98a" />


## How to Run

1. Open the [Wokwi simulation](https://wokwi.com/projects/478881694563573761).
2. Make sure the project includes the **DHT sensor library** and the **ThingSpeak** library.
3. Configure your own ThingSpeak channel and obtain its **Write API Key**.
4. In `sketch.ino`, enter the correct channel ID and your private Write API Key **locally**. Do not commit or share the real key.
5. Start the Wokwi simulation and open the Serial Monitor.
6. Check for the message `Data sent successfully!`.
7. Open the [public ThingSpeak channel](https://thingspeak.com/channels/3550005) to view the temperature and humidity charts.
8. Change the DHT22 values in Wokwi to see how the uploaded readings change.


## Results

The ESP32 successfully connected to Wi-Fi, read temperature and humidity values, and uploaded them to ThingSpeak. The public charts displayed multiple timestamped readings, including changes made to the simulated sensor values. The Serial Monitor reported `Data sent successfully!` after successful uploads.

---

**Prepared by:** Sana Saleh | **University ID:** 12217400
