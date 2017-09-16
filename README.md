Prototype of common OBD diagnostic board. 

Device uses STN1170 chip in QFTP package, form ScanTool company and it is compatible with ELM327, based on information, which can be found in datasheet about this integrated circuit. 

Main assumption about this prototype was to be modular to lower the cost of the device, because only 3 samples can be acquired through ScanTool company, so prototype has two boards. One with STN1170 and necessary components and second one with transceivers, which are required for communication from car to transceivers and then to OBD chip. 

Wireless communication was planned to use RN4870 BLE module. But because of bad implementation (but I am in 90% sure, that module was broken) I can not force him to work properly. In the end it lost MAC address and this is common for modules, based on IS187x Bluetooth LE ICs. Reason for why this happened was as Microchip support claim “Inappropriate module reset”, but I didn’t get answer for my question, when I asked about, how this module should be reset, to prevent such behavior in the future. ANyway I decided to move on and leave this module for now. Finally I decided for HM-13 module. Module is already implemented and I need to do more tweaking in revision 2 to push next revision. For now module is working on revision 1 prototype board.

Wired communication with PC uses CP2102N UART to Bridge ICs. His cost is lower than FTDI chips and has a lot possible ways to configure it, beginning from drivers, ending at ICs internal configuration. Soldering it without hot air station is not easy task to do, but it can be done with some patience, even with recommended layout pattern from datasheet. Now pads have the same width, but they are longer.

Checked protocols:
- [x] HS-CAN 
- [X] MS-CAN 
- [x] SW-CAN 
- [x] K-LINE
- [x] L-LINE
- [ ] J1850 VPW
- [ ] J1850 PWM

Basic connection tested on standard OBD2 connector pinout:
- Fiat Punto MK2 (CAN, K-LINE) 
- Opel Vectra C (HS-CAN, MS-CAN, SW-CAN)
- Citroen DS4 (HS-CAN)

Gallery: https://imgur.com/a/UtiDV

Video: https://youtu.be/GFeOGx49xKc
