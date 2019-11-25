# Temperature-monitoring-using-Cayenne-IOT-Platform
This temperature monitoring system is based on Cayenne Internet of Things (IoT) platform, NodeMCU microcontroller (MCU) and Message Queuing Telemetry Transport (MQTT) protocol. Cayenne IoT Platform contains a vast catalogue of certified IoT-ready devices and connectivity options. This allows users to easily add any device to the library utilising MQTT API. All devices in Cayenne are interoperable and benefit from features such as rules engine, asset tracking, remote monitoring and control, and tools to visualise real-time and historical data.
# Required components
   ESP32 dev module
   
   Jumper wires
   
   Bread Board
   
   DHT11 temperature and humidity sensor

# Circuit Connections

   -ESP32 PIN-OUT TO TEMP SENSOR PINS
   
      D15	                    OUT
      
     3V -VCC	             VCC
     
      Gnd                     Gnd


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

![Cat](https://raw.githubusercontent.com/{user}/{repo}/assets/cat.png)
Copy MQTT username, password and client ID from Create App (Fig. 5). Paste these respective details under username, password and client ID in Arduino source code along with your Wi-Fi name and password.
After successfully compiling and uploading the code toESP32, open Serial Monitor in Arduino IDE. You will see ESP32 connected to Wi-Fi. After the connection is established, the previous page is automatically updated on Cayenne. A new dashboard opens in the browser. Cayenne generates an ID and a device icon for your device you may change it in Settings.
Click on Add new and then Device/Widget in Settings.
When a connection is made, sensor data gets uploaded to Cayenne. Temperature data on Cayenne.


