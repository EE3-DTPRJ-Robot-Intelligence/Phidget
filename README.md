# Phidget
Python script for polling mode pressure sensing with 4 half bridge loadcells

## Prerequisites
### hardware:  
* PhidgetBridge 1046, 
* mini usb cable loadcells, 
* resistors(match the resistance of the strain gauge)

### software:
* Phidget22 library - "libphidget22",
* Python2.7,
* Phidget Python Module

## Wiring Guide

## Install phidget22 library - Linux
1. Fisrt make sure to have libusb-1.0 development libraries installed
  ```bash
  apt-get install libusb-1.0-0-dev
  ```
2. Next, download the libphidget22 package 
[libphidget22](https://www.phidgets.com/downloads/phidget22/libraries/linux/libphidget22.tar.gz)

3. Extract the package, open the README file and follow the instrustions about how to install the files.

3. Libraries are by deauflt installed in /usr/local/lib. If this is not the library path for your system, you can
   
  ...Specify a different folder for installation:
  ```bash
  ./configure --prefix=/usr && make && sudo make install
  ```
  ...or add /usr/local/lib to the system-wide library path:
  ```bash
  echo /usr/local/lib >> /etc/ld.so.conf && sudo ldconfig
  ```
## Install Phidge Python Package

## Event Driven Mode

## Polling Mode
