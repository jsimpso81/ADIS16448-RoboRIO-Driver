# LabVIEW Instructions

## Notes on this version

This version has a new optional input on the Open VI that enables "register read mode".  This mode is intended to bypass the AutoSPI read, which currently has a problem with the 2022 version of the roboRIO FPGA code.

In order to save CPU cycles, this version disables reading the Accel, Mag, and Baro pressure when using register read mode.  Only the X,Y,X gyro readings and IMU temperature are available.

This version re-enables the internal bartlett filter and sets it to the default of 0x02.

This version, like previous versions has a continuous calibration function that continuously collects data for calibration.  When a re-calibration is requested, new calibration constants are calculated and stored immediately.

This version has NOT been tested with the Auto SPI mode.


## NI Package Manager Installation
Installation via the NI Package Manager is the only supported installation method for the 2020 season. 

This library assumes you have a working 2019 or 2020 LabVIEW Professional installation and 2020.b4 or greater FRC software package already installed on your system. The latest package installer can be found [here](https://github.com/jsimpso81/ADIS16448-RoboRIO-Driver/releases). 

## Installing the Library
Once downloaded, double-click on the `.nipkg` file. Chose the correct package for the version of LabVIEW that is being used 2019 or 2020.  The pre-installed NI Package Manager utility will extract the necessary files into the correct folders within your LabVIEW installation. Future updates to the library can be installed over previous installations. **LabVIEW must be closed completely before installing the library package!** 

![ADIS16448 .nipkg Icon](https://raw.githubusercontent.com/jsimpso81/ADIS16448-RoboRIO-Driver/master/images/nipkg_icon.PNG)

Once you double-click on the installer file, the NI Package Manager will walk you through installing the library. Click `Next` at the window shown below to install the library. *Note: The library version shown in the screenshots on this page may be different than the latest version available on the GitHub page!*

![ADIS16448 Installing Window](https://raw.githubusercontent.com/jsimpso81/ADIS16448-RoboRIO-Driver/master/images/installing.PNG)

The package manager window should like like below if the library was installed successfully.

![ADIS16448 Install Complete](https://raw.githubusercontent.com/jsimpso81/ADIS16448-RoboRIO-Driver/master/images/installed.PNG)

## Using the Library
The LabVIEW driver can be used like any other third-party library. All .vi's can be found in the pallet shown below:

![ADIS16448 LabVIEW Pallet](https://raw.githubusercontent.com/jsimpso81/ADIS16448-RoboRIO-Driver/master/images/menu.PNG)

The example .vi included in this repository should look like below when successfully connected to a RoboRIO:

![ADIS16448 LabVIEW Example Front Panel](https://raw.githubusercontent.com/jsimpso81/ADIS16448-RoboRIO-Driver/master/images/labview_example.PNG)

## Uninstalling the Library
To uninstall the library, open the NI Package Manager and select `ADIS16448 IMU RoboRIO Driver`. 

![ADIS16448 .nipkg Icon](https://raw.githubusercontent.com/jsimpso81/ADIS16448-RoboRIO-Driver/master/images/remove_menu.PNG)
