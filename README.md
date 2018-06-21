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

1. Download and unpack the 
[Phidget Python Module](https://www.phidgets.com/downloads/phidget22/libraries/any/Phidget22Python.zip)

   On terminal install the module:
  ```bash
  python setup.py install
  ```

## Event Driven Mode

## Polling Mode
