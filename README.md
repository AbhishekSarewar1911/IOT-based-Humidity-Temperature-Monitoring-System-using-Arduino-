# IOT-based-Humidity & Temperature-Monitoring-System-using-Arduino

## Table of Contents :

- 1 Overview:  IOT-based-Humidity & Temperature-Monitoring-System  using ESP8266 & DHT11 Sensor
- 2 DHT-11 Humidity and Temperature Sensor
- 3 IoT system using ESP8266 wifi Module & DHT-11 temperature Sensor
- 4 Mathematical Calculation to Measure Flow Rate & Volume
- 5 Setting up Thingspeak
- 6 Source Code/Program
- 7 Monitoring Water Flow Rate & Volume and output graph

## Overview: IOT-based-Humidity & Temperature-Monitoring-System  using ESP8266 & DHT11 Sensor
 

In this project, we are using the DHT11 sensor for sending Temperature and Humidity data to Thingspeak using Arduino and ESP8266. By this method, we can monitor our DHT11 sensor’s temperature and humidity data over the internet using the ThingSpeak IoT server. And we can view the logged data and graph overtime on the Thingspeak website.

Here Arduino Uno reads the current temperature and humidity data from DHT11 and sends it to the ThingSpeak server for live monitoring from anywhere in the world. We previously used ThingSpeak with Raspberry Pi and ESP32 to upload the data on the cloud. ThingSpeak is an open data platform for monitoring your data online where you can set the data as private or public according to your choice. ThingSpeak takes a minimum of 15 seconds to update your readings. It's a great and very easy-to-use platform for building IoT projects.

### Components Required
- Arduino Uno
- ESP8266 WiFi Module
- DHT11 Sensor
- Breadboard
- Jumper Wires
 
 

# DHT-11 Humidity and Temperature Sensor

The DHT11 sensor can either be purchased as a sensor or as a module. Either way, the performance of the sensor is same. The sensor will come as a 4-pin package out of which only three pins will be used whereas the module will come with three pins as shown above.

The only difference between the sensor and module is that the module will have a filtering capacitor and pull-up resistor inbuilt, and for the sensor, you have to use them externally if required.

 

### Where to use DHT11:
The DHT11 is a commonly used Temperature and humidity sensor. The sensor comes with a dedicated NTC to measure temperature and an 8-bit microcontroller to output the values of temperature and humidity as serial data. The sensor is also factory calibrated and hence easy to interface with other microcontrollers.

The sensor can measure temperature from 0°C to 50°C and humidity from 20% to 90% with an accuracy of ±1°C and ±1%. So if you are looking to measure in this range then this sensor might be the right choice for you.
  ![Alt Text](https://github.com/AbhishekSarewar1911/IOT-based-Humidity-Temperature-Monitoring-System-using-Arduino-/blob/main/DHT11-Sensor.jpg)  ![Alt Text](https://github.com/AbhishekSarewar1911/IOT-based-Humidity-Temperature-Monitoring-System-using-Arduino-/blob/main/DHT11%E2%80%93Temperature-Sensor-Pinout.jpg)

 
## How to use DHT11 Sensor:
The DHT11 Sensor is factory calibrated and outputs serial data and hence it is highly easy to set it up. The connection diagram for this sensor is shown below.

![Alt Text](https://github.com/AbhishekSarewar1911/IOT-based-Humidity-Temperature-Monitoring-System-using-Arduino-/blob/main/Circuit-using-DHT11%E2%80%93Temperature-Sensor.png)
 
As you can see the data pin is connected to an I/O pin of the MCU and a 5K pull-up resistor is used. This data pin outputs the value of both temperature and humidity as serial data. If you are trying to interface DHT11 with Arduino then there are ready-made libraries for it which will give you a quick start.
 
 
 
 # Circuit and connections using ESP8266 & DHT11 Sensor
 
 Circuit diagram for monitoring humidity and temperature is shown in Figure below It is built around Arduino MCU, DHT11 sensor and ESP8266 Wi-Fi module.
 
 ![Alt Text]()
 
 The DHT11 sensor senses humidity and temperature, and sends the information to digital pin 5 of Arduino MCU, as shown in Fig. 2. From Arduino MCU, humidity and temperature values are uploaded to the Cloud at regular intervals of time through ESP8266 Wi-Fi module. From the Cloud, humidity and temperature values can be seen graphically on ThingSpeak platform from anywhere in the world.
  ![Alt Text]()

 
 # Mathematical Calculation to Measure Flow Rate & Volume



 # Setting up Thingspeak

Now we need to setup the Thingspeak Account. To set up Thingspeak follow the following Steps:
 ![Alt Text](https://github.com/AbhishekSarewar1911/IOT-basedWater-Monitoring-System-using-waterflow-yf-s201-sensor-and-8266-nodeMCU-microcontroller-/blob/main/thingspeak.png)
 
 - Step 1: Visit https://thingspeak.com/ and create your account by filling up the details.
 - ![Alt Text](https://github.com/AbhishekSarewar1911/IOT-basedWater-Monitoring-System-using-waterflow-yf-s201-sensor-and-8266-nodeMCU-microcontroller-/blob/main/waterflow_channel.png)
 - Step 2: Create a New Channel by Clicking on “Channel” & fill up the following details as shown in the image below.
 - ![Alt Text](https://github.com/AbhishekSarewar1911/IOT-basedWater-Monitoring-System-using-waterflow-yf-s201-sensor-and-8266-nodeMCU-microcontroller-/blob/main/waterflowAPI.png)
 - Step 3: Click on API Key, you will see the “Write API Key“. Copy the API Key. This is very important, it will be required in Code Part.
 - Step 4: You can click on the “Private View” & customize the display window as you want.

 So, that’s all from the Thingspeak Setup Part. Now let us move to the programming Part.

 # Source Code/Program
 
Now Let us see ESP8266 Water Flow Sensor Code using Arduino IDE. The code can be directly uploaded to the NodeMCU Board. But before that we need few Libraries for OLED Display. So download the Library first and add it to the Arduino IDE.

 

> Download SSD1306 Library

> Download Adafruit GFX Library 

 
> 1.String apiKey = “I4T8HSIGTOLPHUPE”;

> const char *ssid = “Water_Monitor”; 

> const char *pass = “YF-2019”;
 

Change the Thingspeak API Key, Wifi SSID & Password from the line above.

Now go through the source code given: https://github.com/AbhishekSarewar1911/IOT-basedWater-Monitoring-System-using-waterflow-yf-s201-sensor-and-8266-nodeMCU-microcontroller-/blob/main/Water%20Flow%20reading%20code.c


# Monitoring Water Flow Rate & Volume In ThingSpeak
 

Once the Code is uploaded the OLED Display will start working and will show the flow rate and volume. Initially the flow rate will be 0 liter/minute(L/M). Also Total Volume shown will be 0 Liter(L).
![Alt Text](https://github.com/AbhishekSarewar1911/IOT-basedWater-Monitoring-System-using-waterflow-yf-s201-sensor-and-8266-nodeMCU-microcontroller-/blob/main/Iot-Water-Flow-Meter-SETUP.jpg)
 

Once the motor is turned ON & Water Starts flowing, you can see the OLED Display displaying the Flow Rate (F) & Volume(V).

## OUTPUT GRAPH

![Alt Text](https://github.com/AbhishekSarewar1911/IOT-basedWater-Monitoring-System-using-waterflow-yf-s201-sensor-and-8266-nodeMCU-microcontroller-/blob/main/Water-Flow-Sensor-Thingspeak2.jpg)

### thankyou!
