# Eachine-Tyro79-BF422-settings
Better default starting point for configuration of new quad copter.

Click the "view code" button.

It's become apparent that the Tyro97 has been shipped with more than one Flight Controller, the link below shows this product on Banggood:
https://uk.banggood.com/Eachine-Wizard-X140HV-140mm-FPV-Racing-Drone-Frame-Spare-Part-Betaflight-F4-Flight-Controller-OSD-w-or-5V-or-1A-BEC-20x20mm-p-1471337.html?gmcCountry=GB&currency=GBP&createTmp=1&utm_source=googleshopping&utm_medium=cpc_bgs&utm_content=lijing&utm_campaign=ssc-gb-all-0804-newcustom&ad_id=454095793613&gclid=EAIaIQobChMI85ur7tfz6wIV2uDVCh2-8wS1EAEYASABEgJx_PD_BwE&cur_warehouse=CN

General settings for the Eachine Tyro79 running BetaFlight 4.2.2. 
This setup is for the newer kit including the generic flight controller with 3 pin camera connector and unlabelled 4 pin connector near LED pads.

Files in this repository include: 
Stock PIDs and Filtering. 
4k PID loop. 
Bi-directional DSHOT300 (requires JESC firmware). 
SBUS serial receiver on SBUS pin (FRSKY). 
Soft serial for S.Port telemetry on motor 6 pad. 
Analog RSSI on RSSI pad (A00). 
TBS smart audio on UART 2TX (wire directly from VTX to FC).
VTX table for XF5805_V6 video transmitter. 
4 LEDs enabled.

Notes: 
You must short the RX jumper next to the RX connector to either SBUS or PPM, connect either outside pad to the middle pad with a blob of solder. 
Analog RSSI is not configured by default using the MATEKF411 custom defaults. (use this if connecting RSSI output from RX)
This FC will NOT run an 8k PID loop, use 4k plus DSHOT300.
This kit may come with a wrongly pinned VTX cable! 
Check connector against VTX silk screen, connect "DATA" on VTX to UART 2 TX (TX2) pad. 

FC VTX connector has the following pinout: 
1,GND 
2,+V (5V reg) 
3,Video 
4,TBS SP (TX2)

My flight controller arrived DOA, No SBUS channels even with 3 different recievers.
After some time with an oscilloscope it turned out that the inverter was not working as it should.
The quickest solution was to remove and bridge a resistor that sits between the inverter and the STM chip.
The problem is that the inverter is pulled up too hard and the LOW signal is only 0.5v less than a high signal. 
Bridging the offending resistor allows more current to flow to the micro and restores the signal to the correct logic levels.
Before making any changes to the FC, touch both sides of the resistor with metal tweezers whilst monitoring the channels tab in the configurator.
See DOA SBUS FIX.jpg

Usage:
Flash FC with BF 4.2.2 (MATEKF411)
Restoring the json file in the configurator will give you the setup including my control layout using an SBUS reciever (FRSKY XSR-M).
Copy contents of TXT file into CLI to apply the differences between my setup and the default Betaflight setup. PRESS ENTER.
Reboot, CALIBRATE ACCELEROMETER, customize.
FLY, CRASH, REBUILD, REPEAT!

ToDo:
Work out the connections on the mystery connector.


I hope you find this project helpful, maybe it's worth a coffee?              
https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=NJBUQDTZUTCTW&source=url
