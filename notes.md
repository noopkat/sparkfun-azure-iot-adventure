1. Download and install Arduino IDE
2. Install board via https://github.com/esp8266/Arduino
3. Install the libraries needed - https://github.com/noopkat/connectthedots/blob/master/Devices/DirectlyConnectedDevices/ESP8266/ESP8266_setup.md (for now, pin to version 1.0.17 of each library)
3. Click the 'Deploy to Azure' button in our instructions
4. Create a new device in the newly created IoT hub
5. Grab the connection string
6. Put device name and connection string into connect the dots cpp file
7. Put wifi credentials into ino file
8. Upload to Sparkfun Thing dev board 
9. Check azure web app to see if data is coming through

Deploy to Azure button is ready to copy paste below:


[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](http://azuredeploy.net/?repository=https://github.com/noopkat/connectthedots/raw/IoTHubManagement/Azure/ARMTemplate)
