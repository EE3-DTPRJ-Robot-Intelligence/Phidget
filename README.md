# Phidget
Python script for polling mode pressure sensing with 4 half bridge loadcells

## Prerequisites
### hardware:  
* PhidgetBridge 1046, 
* mini usb cable loadcells, 
* resistors(match the resistance of the strain gauge)

### software:
* Phidget22 library - "libphidget22",
* Python2.7 or 3.6,
* Phidget Python Module

## Wiring Guide
Depends on whtat type of loatdcells you are using, additional wiring migh be required.Please check your spec sheet:

For half-bridge loadcells, you need to complete the circuit with two resistors at the same resistance as the strain gauge:
![alt-text](https://www.xsimulator.net/community/attachments/30j0d2t-jpg.24306/)
If you are not sure what resistance to pick, measure between the white and the red line, and between the balck and the red line. Pick the same resistance for the resistors, and complete the circuit as shown above.
Input+ and Input- are power line, which should be connected to the 5V and Ground on the phidget.
OUtput A and output b are excitation signal and should be connected to "+" and "-" pins. 
## Install phidget22 library - Linux
1. Fisrt make sure to have libusb-1.0 development libraries installed
   ```bash
   apt-get install libusb-1.0-0-dev
   ```
2. Next, download the 
[libphidget22](https://www.phidgets.com/downloads/phidget22/libraries/linux/libphidget22.tar.gz)
package
3. Extract the package, open the README file and follow the instrustions about how to install the files.

3. Libraries are by deauflt installed in /usr/local/lib. If this is not the library path for your system, you can

   a. specify a different folder for installation:
   ```bash
   ./configure --prefix=/usr && make && sudo make install
   ```
  
   b. or add /usr/local/lib to the system-wide library path:
  
   ```bash
   echo /usr/local/lib >> /etc/ld.so.conf && sudo ldconfig
   ```
4. To verify that the libraries are properly installed, download the 
[HelloWorld C example](https://www.phidgets.com/downloads/phidget22/examples/c/Manager/Phidget22_HelloWorld_C_Ex.zip)

   Compile and run the example:
   ```bash
   gcc HelloWorld.c -o HelloWorld -lphidget22
   ```
   ```bash
   ./HelloWorld
   ```
   Your output should look like this:
   ![alt-text](https://www.phidgets.com/docs/images/1/1a/Linux_helloworld.PNG)
   
   
   for other more detailed information or other OS please go to [https://www.phidgets.com/docs/OS - Linux](https://www.phidgets.com/docs/OS_-_Linux#Getting_Started_with_Linux)
   
## Install Phidge Python Module
Other languages are also supported: 
[C](https://www.phidgets.com/docs/Language_-_C),
[Java](https://www.phidgets.com/docs/Language_-_Java) 

For Python:

Download and unpack the 
[Phidget Python Module](https://www.phidgets.com/downloads/phidget22/libraries/any/Phidget22Python.zip)

On terminal install the module:
```bash
python setup.py install
```

Now you can connect your phidget and run the script.

## Event Driven Mode
The original example code from Phidget website only is event driven. Only when there is a change in the input that meets the criteria will there be an output on the terminal. You can download the code
[here](https://www.phidgets.com/downloads/phidget22/examples/python/VoltageRatioInput/Phidget22_VoltageRatio_Python_Ex.zip)

## Polling Mode
In our case we want to run phidget in polling mode so that we can monitor all four channels simultatiously at each clock cycle.The file *AllChannels.py* is the modified version of the example code that serves the need. The serial number can be changed in the script to match your devices.
```python
" Set matching parameters to specify which channel to open"
ch0.setDeviceSerialNumber(494011)
ch0.setChannel(0)
ch1.setDeviceSerialNumber(494011)
ch1.setChannel(1)
ch2.setDeviceSerialNumber(494011)
ch2.setChannel(2)
ch3.setDeviceSerialNumber(494011)
ch3.setChannel(3)
```

