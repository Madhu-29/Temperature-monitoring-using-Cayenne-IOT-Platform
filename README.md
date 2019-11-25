# Temperature-monitoring-using-Cayenne-IOT-Platform
This temperature monitoring system is based on Cayenne Internet of Things (IoT) platform, ESP32 microcontroller (MCU) and Message Queuing Telemetry Transport (MQTT) protocol. Cayenne IoT Platform contains a vast catalogue of certified IoT-ready devices and connectivity options. This allows users to easily add any device to the library utilising MQTT API. All devices in Cayenne are interoperable and benefit from features such as rules engine, asset tracking, remote monitoring and control, and tools to visualise real-time and historical data.
# Required components
   ESP32 dev module
   
   Jumper wires
   
   Bread Board
   
   DHT11 temperature and humidity sensor

# Circuit Connections

   -ESP32 PIN-OUT TO TEMP SENSOR PINS
   
      D15	                    OUT
      
     3V -VCC	              VCC
     
      Gnd                      Gnd


# Esp32 programming with Arduino IDE

You need Arduino IDE software to program ESP32. Download the latest Arduino IDE from the official Arduino and install it on your computer.
Steps for adding ESP32 board and library to Arduino IDE are given below.
1.	Open Arduino IDE. Go to File menu and select Preferences.
2.	Copy this packege and paste in Additional Boards Manager URL.
    https://dl.espressif.com/dl/package_esp32_index.json
3.	Go to Tools and select Boards Manager.
4.	Type esp32 in search box and press Enter.
5.	Install the latest version.
6.	From Tools menu, select ESP32 DEV module) board.
7.	Select Include Library from Sketch menu.
8.	Click on Add ZIP Library and add Cayenne-MQTT-ESP-master zip file, or directly copy the folder (Cayenne-MQTT-ESP-master) and paste it in Libraries folder of Arduino IDE.

# Software
The source code to program esp32 is written in Arduino programming language. ESP32 is programmed using Arduino IDE software. Open Arduino IDE and select the correct board from Tools Board menu in Arduino IDE.
The source code starts with #define CAYENNE_PRINT Serial and #include <CayenneMQTTESP8266.h>

Here, CayenneMQTTESP8266.h header file is used to interface ESP32 with [CAYENNE](https://cayenne.mydevices.com)

Cayenne.begin( ) is used to connect Wi-Fi and Cayenne dashboard with ESP32.

Cayenne_out_default() and Cayenne.virtualWrite() are used for writing sensor data on channel number 1.

Serial.begin(9600) function initialises the serial port with a baud rate of 9600.

Enter your Wi-Fi name and password in the source code, as indicated by xxxxx below. Also provide other details in the source code, such as username, password and client ID obtained from Cayenne as explained in the next section.
>define CAYENNE_PRINT Serial

>include <CayenneMQTTESP8266.h>

// WiFi network info.

>char ssid[] = “xxxxx”; //put your own ssid
>char wifiPassword[] = “xxxxx”; //put your

wifi password
// Cayenne authentication info. This should
be obtained from the Cayenne Dashboard.

```c
char username[] = “xxxxx”;

char password[] = “xxxxx”;

char clientID[] = “xxxx”;
```

After adding all details in the code, compile it and upload the program (sketch) using a standard USB cable to ESP32.

# Hardware interfacing with Cayenne IoT platform

# STEP-1:
To interface the circuit with the IoT platform, open this link on any browser. Click on Sign Up Free. Fill all the fields and click on Get Started Free.

![alt-text](https://github.com/Madhu-29/Temperature-monitoring-using-Cayenne-IOT-Platform/blob/master/CAYENNE-1.jpg)
# STEP-2:
Next, click on Bring Your Own Things (Fig. 4) from Cayenne API.
![alt-text](https://github.com/Madhu-29/Temperature-monitoring-using-Cayenne-IOT-Platform/blob/master/CAYENNE-2.jpg)
# STEP-3:
Copy MQTT username, password and client ID from Create App. Paste these respective details under username, password and client ID in Arduino source code along with your Wi-Fi name and password.
![alt-text](https://github.com/Madhu-29/Temperature-monitoring-using-Cayenne-IOT-Platform/blob/master/CAYENNE-3.jpg)
# STEP-4:
After successfully compiling and uploading the code toESP32, open Serial Monitor in Arduino IDE. You will see ESP32 connected to Wi-Fi. After the connection is established, the previous page is automatically updated on Cayenne. A new dashboard opens in the browser. Cayenne generates an ID and a device icon for your device you may change it in Settings.
![alt-text](https://github.com/Madhu-29/Temperature-monitoring-using-Cayenne-IOT-Platform/blob/master/CAYENNE-4.jpg)
# STEP-5:
Click on Add new and then Device/Widget in Settings.
![alt-text](https://github.com/Madhu-29/Temperature-monitoring-using-Cayenne-IOT-Platform/blob/master/CAYENNE-5.jpg)
# STEP-6:
When a connection is made, sensor data gets uploaded to Cayenne. Temperature data on Cayenne.
![alt-text](https://github.com/Madhu-29/Temperature-monitoring-using-Cayenne-IOT-Platform/blob/master/CAYENNE-6.jpg)
# STEP-7:
You can get a graphical representation of temperature data by clicking on the encircled icon.
![alt-text](https://github.com/Madhu-29/Temperature-monitoring-using-Cayenne-IOT-Platform/blob/master/CAYENNE-7.jpg)

# NOTE
Temperture monitoring can also be done using other IOT platforms like [Thingspeak](),[Adafruit](),[firebase](),asksensors etc.


