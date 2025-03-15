# M1_rs232
RS-232 interface board for the TRS-80 Model I Expansion Interface

![image](https://github.com/user-attachments/assets/7a44d132-25f3-436f-8121-187a92cc4494)

I created this design partly out of necessity, as original Radio Shack serial interfaces are scarce, and as a project to learn KiCad.

This design replicates the operation of the original board, ensuring compatibility with existing Model I software. Hardware-wise, there are a few differences:
  1. SMT components are used wherever possible, to minimize cost
  2. Sense switch (DIP switch configuration) functionality is removed, so that the interface must be configured via software
  3. The TERM/COMM switch has been removed. The unit is in TERM mode, and an external null-modem adapter must be used if operation as a DCE device is required.
  4. IC selection eliminated the need for +12/-12/-5 supply rails. +5V is the only supply needed.
