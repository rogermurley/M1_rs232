# M1_rs232
RS-232 interface board for the TRS-80 Model I Expansion Interface, version 2.1

![ver2 1onwhite](https://github.com/user-attachments/assets/f19f780a-49bd-477e-9bf6-7d73497f70b4)

### If you would like to purchase turnkey assembled and tested units, please visit my site at https://byteshiftmusic.com/trs-80-model-i-rs-232-interface-re-creation/

I also have available a PCB for adapting the 40-pin edge card (J1) on the Expansion Interface to an IDC26 header, so that a standard PC parallel port DB25 pigtail can be used. Please see the link above for those, as well.

I created this design partly out of necessity, as original Radio Shack serial interfaces are scarce, and partly as a project to learn KiCad.

This design replicates the operation of the original board, ensuring compatibility with existing Model I software. Hardware-wise, there are a few differences:
  1. SMT components are used wherever possible, to minimize cost
  2. Sense switch (DIP switch configuration) functionality is removed, so that the interface must be configured via software
  3. The TERM/COMM switch has been removed. The unit is configured in TERM (DTE) mode, and an external null-modem adapter must be used if operation as a DCE device is required.
  4. IC selection eliminated the need for +12/-12/-5 supply rails. +5V is the only supply needed.

Version 2.1 fixes a nasty error which caused the line driver (U9) to be in permanent shutdown mode, fixes some minor mechanical interference between the PCB and the expansion interface's chassis, and adds some quality of life enhancements, such as:
 1. A jumper for RS-232 TX/RX loopback was added for ease of testing
 2. A breakout header for TTL-level TX and RX was added, for ease in interfacing to an ESP8266 running [WiFiModem firmware](https://github.com/dhansel/WifiModem)
 3. A breakout header for +5VDC and GND was added for powering the previously mentioned ESP8266
 4. A jumper for disabling the RS-232 transceiver was added, for use when using an internal TTL-level device

BOM notes:
  1. J1 is PCB fingers on the underside of the board, which press-fit against the Expansion Interface add-on connector.
  2. J2, J3, J4, and J5 are standard 2.54mm pitch single row headers, 11 pins in total
  3. Y1 must be an AT-cut series type crystal with an ESR of <= 50 ohms in order to function properly with the 8116 baud rate generator.
  4. U1 and U2 must be purchased used or as old stock. Ebay is a good source.

![ver2 1rendertop](https://github.com/user-attachments/assets/b976ff87-9051-41f3-b0d4-23632e2d3a72)
![ver2 1renderbottom](https://github.com/user-attachments/assets/cc7605ea-8bd6-4db8-8544-185ae1ba39f9)
