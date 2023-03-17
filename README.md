# Final-Project---Pan-and-Tilt

The purpose of this project is to create a thermal imaging pan and tilt system for a drone.  
There are multiple programs that must interact together in order to achieve this goal. As of right now the project is not 100% complete.

The way things should work is described below:

Servo Control: 
-Jetson Nano (raspberry pi 4 was used during development) recieves input from a controller (PS5 controller was used during development)
-Controller commands are sent to a Raspbery Pi Pico using SPI
-Raspberry Pi Pico recieves SPI from Jetson Nano and sends them to an adafruit 16-channel 12-bit pwm/servo driver using I2C*
-adafruit 16-channel 12-bit pwm/servo driver is connected to 2 servomotors

*Info on how to interface with the motordriver can be found here: https://learn.adafruit.com/16-channel-pwm-servo-driver/downloads

All code has been written in Python.
The Raspberry Pi Pico is currently setup to run on Circuit Python. 
At the moment only partial functionality as been achieved. The Raspberry Pi 4 is able to recieve commands from the controller but is unable to transmit them to the Pico. In order to continue making progress the servomotor driver is currently recieving its input directly from the Raspberry Pi 4.

The code that the Raspberry Pi 4 uses to inputs from the PS5 controller can be found in the Controller Code Folder. More information can be found in the CONTROLLER_READ_ME.txt file within the folder.

There is a program written that continuously sends pre-coded commands from the Raspberry Pi Pico to the motordriver. This, along with another read me file, can be found in the Microcontroller Code folder.

************************************************************************

SPI Communication:
In the SPI Test folder a program that continuously sends a SPI command from the Raspberry Pi 4 can be found. This was used to test the Raspberry PI 4's ablility to transmit SPI to the Raspberryy Pi Pico. So far this has been unsuccessful. 

In the microcontroller code folder more programs can be found that are attempted to recieve SPI commands from the Raspberry Pi 4. This has also bee unsuccessful.

************************************************************************

Thermal Imaging:

In the Flir_Cam-Python_Code folder there is a program that allows the user to capture and save images from a USB webcam. In this case we are using a Flir Lepton
3.5 Thermal Camera. Images are currently being captured using mouse and keyboard. More information can be found in the Flir_READ_ME file within the folder.
