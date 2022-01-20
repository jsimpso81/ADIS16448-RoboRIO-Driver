# ADIS16448 IMU Interface Library for FIRST Robotics


### NOTE: This is copy of the main repository with an updated LabVIEW driver to work around the 2022 Auto SPI issue.

## Introduction

These libraries allow mentors, students, and engineers to quickly get started using the ADIS16448 Inertial Measurement Unit (IMU). This compact module provides teams with a high-performance, ten-degree-of-freedom (DoF), calibrated, feedback for their FRC robots. The module packages several gyroscopes and accelerometers in a small, robust package, perfect for high-performance robotics (such as FRC). 

<p align="center">
  <img src="https://raw.githubusercontent.com/jsimpso81/ADIS16448-RoboRIO-Driver/master/images/448_IMU.jpg" alt="ADIS16448 Breakout Board for FRC" width="60%%" />
</p>

To simplify the library as much as possible for the 2020 season, only a few, key IMU features are exposed to the user by default. 

These software libraries provide the user (you) with:

- X, Y, and Z Integrated Gyroscope Outputs  calculated from 16-bit register outputs
- IMU register reads and writes using discrete SPI transactions and the Auto SPI peripheral built into the FRC 2020 RoboRIO image
- IMU heading initialization and continuous bias compensation routines
- Complementary filter outputs useful for measuring X-Y tilt  (This is currently disabled on the LabVIEW driver.)

Tutorial videos, how-to guides, and additional resources can be found on the [ADI FIRST Robotics Wiki Page](https://wiki.analog.com/first/first_robotics_donation_resources).

## How do I install this library?

The IMU driver currently supports all three official FRC languages (C++, Java, and LabVIEW). 

#### C++ and Java Users (Online Install): 

The C++ and Java drivers have been removed from this library.  This respository only contains the LabVIEW driver with the Auto SPI problem work around.


#### C++ and Java Users (Offline Install): 
An offline installation option is available for users whose machines do not have acces to the internet:

The C++ and Java drivers have been removed from this library.  This respository only contains the LabVIEW driver with the Auto SPI problem work around.

#### LabVIEW Users:

LabVIEW libraries should be installed using the NI Package Manager. Check out the releases page for the latest package installer.

https://github.com/jsimpso81/ADIS16448-RoboRIO-Driver/releases

Additional LabVIEW instructions and API details can be found in the LabVIEW subdirectory in this repository. 

https://github.com/jsimpso81/ADIS16448-RoboRIO-Driver/tree/master/LabVIEW

## Is the API documented?

The LabVIEW VIs have built in help via Ctrl-H.

## Can I order my own PCB? Where can I find details about the circuit board?
The schematic, layout, and manufacturing files can be found in this repository under `hardware/PCB Reference Files/`. 
Copies of this board may be purchased from OSH Park by following this [link](https://oshpark.com/shared_projects/G8nquDEx).

## What do I need to get started?

To use the software, you need access to a RoboRIO and the ADIS16448 RoboRIO Breakout Board. This software is based on the FRC 2020 software distribution and relies on the latest WPILib libraries and RoboRIO image to interface with the IMU. Previous (pre-2020) versions of LabVIEW and WPILib libraries are **not** supported. 

Plug in the expansion board as shown below. **Be careful not to offset the connector!!** If installed correctly, the Power LED should turn on once the RoboRIO is powered on. If your board has a status LED, it will only light up once the IMU has successfully communicated with the RoboRIO.

**Your RoboRIO should be imaged to match the version of the NI Update Suite installed on your PC.** For example, if you have the latest (of this writing) update suite installed (2020.0.0), then you must also have the **FRC_roboRIO_2020_v10** image and **roboRIO_6.0.0f1** firmware installed. This driver relies heavily on the FPGA image loaded in the RoboRIO and _**will not work**_ on older versions. The most current NI Update Suite can be found [here](https://www.ni.com/en-us/support/downloads/drivers/download.frc-game-tools.html#333285).

![ADIS16448 Breakout Board Installed on a RoboRIO](https://raw.githubusercontent.com/jsimpso81/ADIS16448-RoboRIO-Driver/master/images/IMG_5514.JPG)

**This version of the driver uses the FGPA get time routine that is part of the Trajectory/Control Library found here https://github.com/jsimpso81.**  This could be replaced with the WPILIB get FPGA time routine, which will experience time wrap around issues if the roboRIO is left on for more than approx 70 minutes.
