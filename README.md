# Eachine-Tyro79-BF422-settings
Better default starting point for configuration of new quad copter.

General settings for the Eachine Mantis79 running BetaFlight 4.2.2. 
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
You must short the RX jumper next to the RX connector to either SBUS OR PPM, connect either outside pad to the middle pad with a blob of solder. 
Analog RSSI is not configured by default using the MATEKF411 custom defaults. (use this if connecting RSSI output from RX)
This kit may come with a wrongly pinned VTX cable! 
Check connector against VTX silk screen. 
FC VTX connector has the following pinout: 
1 GND 
2 +V (5V reg) 
3 Video 4 
TBS SP (TX2)

Usage:
Flash FC with BF 4.2.2 (MATEKF411)
"restore" Json file in configurator.
Copy contents of TXT file into CLI.
Reboot, customize.
