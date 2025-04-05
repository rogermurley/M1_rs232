# M1_rs232
RS-232 interface board for the TRS-80 Model I Expansion Interface, version 1.1

![image](https://github.com/user-attachments/assets/957077d5-4cde-4494-880d-45691ff9e3f8)

I created this design partly out of necessity, as original Radio Shack serial interfaces are scarce, and as a project to learn KiCad.
Version 1.1 fixes a nasty error which caused the line driver (U9) to be in permanent shutdown mode.  It also fixes some minor mechanical interference between the PCB and the expansion interface's chassis.

This design replicates the operation of the original board, ensuring compatibility with existing Model I software. Hardware-wise, there are a few differences:
  1. SMT components are used wherever possible, to minimize cost
  2. Sense switch (DIP switch configuration) functionality is removed, so that the interface must be configured via software
  3. The TERM/COMM switch has been removed. The unit is configured in TERM (DTE) mode, and an external null-modem adapter must be used if operation as a DCE device is required.
  4. IC selection eliminated the need for +12/-12/-5 supply rails. +5V is the only supply needed.

BOM notes:
  1. U3 is a DIP 74LS155 only because I had DIP 74LS155s in my inventory.
  2. J1 is PCB fingers on the underside of the board, which press-fit against the Expansion Interface add-on connector.
  3. Y1 must be an AT-cut crystal with an ESR of <= 50 ohms in order to function properly with the 8116 baud rate generator.

Please stay tuned for version 2 of this board, which will add a few quality-of-life enhancements:
  1. U3 will be changed to an SMT part to match
  2. a jumper for RXD/TXD loopback will be added for ease of testing
  3. jumpers for disabling the line driver, and breakout headers for TTL-level signals will be added, for the easy addition of an ESP8266-based WiFimodem internally
  4. headers for VCC and Gnd will also be added, for the same reason

![image](https://github.com/user-attachments/assets/92e6d287-44f9-453f-8f8f-92b92f035214)
