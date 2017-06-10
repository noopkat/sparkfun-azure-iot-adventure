# sparkfun-azure-iot-adventure
✨🎉🌦⚡🌠
## Introduction

## Install Software

[Visual Studio Code](https://code.visualstudio.com/)

We'll be using Visual Studio code to simply edit any files thanks to it's native Node.js support and understanding of the languages we'll be using today.

[Arduino IDE](https://www.arduino.cc/en/Main/Software)

The Arduino IDE allows us to develop and program new firmware to the embedded device (ESP8266 Thing Dev).

[Git](https://git-scm.com/downloads)

Git is a free and open source distributed version control system, we'll be using it today to pull down baseline code which we'll modify to fit your project.

### Download the Repository
[ConnectTheDots.io](https://github.com/Azure/connectthedots) is an open source project created by Microsoft to help you get tiny devices connected to Microsoft Azure IoT and to implement IoT solutions that take advantage of Microsoft Azure and IoT Hub.

Open up a command prompt / terminal window, navigate to the desired directory for the the project and run the following command to pull down the repository:

```git clone https://github.com/noopkat/sparkfun-azure-iot-adventure```

Git is highly recommended since it is easy to track your modifications to your project. If you prefer to download a .zip file containing the project/tutorial you may download it here:

[https://github.com/noopkat/sparkfun-azure-iot-adventure/archive/master.zip](https://github.com/noopkat/sparkfun-azure-iot-adventure/archive/master.zip)

## Setup Software / Board Support Package
We'll need to set up the Arduino IDE to match our hardware download some libraries to start interacting with Azure / IoT Hub.

Open up your SparkFun box and insert the ESP8266 module into the breadboard as shown.
![ESP8266 Setup](./images/esp8266_turn_on.png)
Plug in your SparkFun Think ESP8266 to an available USB port using the provided cable and turn the power ON by using the indicated switch on the device. The power LED indicator should light red.

## Install ESP8266 Board Support Package
Since the ESP8266 is a relatively new device we'll need to install some optional packages to instruct the Arduino environment on how to compile/program the board.

Open up the Arduino IDE and select `File->Preferences` to open up the preferences window and paste the following URL.
`http://arduino.esp8266.com/stable/package_esp8266com_index.json`
![ESP8266 Board Support Package Repository](./images/arduino_install_esp8266.png)

The Arduino IDE now is pointing at a repository contianing the necessary packages for our board, use the Boards Manager to install the `esp8266` package by selecting `Tools->Board->Boards Manager...`
![ESP8266 Boards Manager Menu](./images/arduino_boards_manager_menu.png)

Type `esp8266` into the search bar as indicated and click the install button to download the package.
![ESP8266 Boards Manager Install](./images/arduino_boards_manager_install.png)

Since the Board Support Package is installed our development environment we can now target the board properly, select `Tools->Board->SparkFun ESP8266 Thing Dev` in the Arduino IDE.

![Arduino Board Selection](./images/arduino_board_selection.png)

## Install Library Dependencies
Open the file Devices\DirectlyConnectedDevices\ESP8266\connect_the_dots\connect_the_dots.ino in the Arduino IDE.

For this project, we'll  need the below libraries. To install them, click on the `Sketch -> Include Library -> Manage Libraries`. Search for each library using the box in the upper-right to filter your search, click on the found library, and click the "Install" button. 

We'll be using specific versions of the Azure tools for this project, please make sure to select the appropriate version when downloading.

 - DHT Sensor Library *(latest)*
 - Adafruit Unified Sensor *(latest)*
 - ArduinoJSON *(latest)*
 - AzureIoTHub *(1.0.17)*
 - AzureIoTUtility *(1.0.17)*
 - AzureIoTProtocol_MQTT *(1.0.17)*

![Install Specific Versions of Libraries](./images/arduino_library_version.png)

## Create an Azure Account
If you are taking this workshop in person you should have received a pass with $50 worth of Azure credit to get you started. You may need to create a Microsoft account at this point if you don't already have one. 

If you have an active Azure account then you may skip this step.

![Microsoft Azure Signup Page](./images/azure_pass_signup.png)

## Deploy to Azure (TBA)
## fixme - should have explanation of what deploy script is actually doing ##
[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](http://azuredeploy.net/?repository=https://github.com/noopkat/connectthedots/raw/IoTHubManagement/Azure/ARMTemplate)

## Create a new IoT Hub Device


## Modify the Code (fix me - reference since ripped from https://github.com/Azure/connectthedots/blob/master/Devices/DirectlyConnectedDevices/ESP8266/ESP8266_setup.md for now)
- In the connect_the_dots.ino file, look for the following lines of code:

```
static char ssid[] = "[Your WiFi network SSID or name]";
static char pass[] = "[Your WiFi network WPA password or WEP key]";
```

- Replace the placeholders with your WiFi name (SSID), WiFi password, and the device connection string you created at the beginning of this tutorial. Save with `Control-s`
- Open up the file `connect_the_dots.cpp`. Look for the following lines of code and replace the placeholders connection information (this is the Device information that you've created when adding a new device id in the IoT Hub device registry):

```
static const char* deviceId = "[deviceid]";
static const char* connectionString = "[connectionstring]";
```

- You can also change the location, organization and displayname values to the ones of your choice
- Save all changes

### Compile and deploy the sample

- Select the COM port on the Arduino IDE. Use **Tools -&gt; Port -&gt; COM** to select it.
- Use **Sketch -&gt;  Upload** on Arduino IDE to compile and upload to the device.

At this point your device should connect to Azure IoT Hub and start sending telemetry data to your ConnectTheDots solution.

## References (notes for now)
Arduino / ESP8266 setup portions from the ctd doc
https://github.com/Azure/connectthedots/blob/master/Devices/DirectlyConnectedDevices/ESP8266/ESP8266_setup.md