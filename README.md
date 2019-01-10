Prototype of common OBD diagnostic board. 

Device uses STN1170 chip in QFTP package, form ScanTool company and it is compatible with ELM327, based on information, which can be found in datasheet about this integrated circuit. 

Main assumption about this prototype to be a modular to lower the cost of the device, because only 3 samples can be acquired through ScanTool company, so prototype has two boards. One with STN1170 and necessary components and second one with transceivers, which are required for communication with proper protocols and OBD chip, but also contains wireless and wired communication. 

Wireless communication was planned RN4870 BLE module. But because of bad implementation (???) or module was broken I can not force him to work properly. In the end it lost MAC address and this is common for modules, based on IS187x Bluetooth LE ICs and the main reason for it was as Microchip support claim “Inappropriate module reset”, but I didn’t get answer for my question, when I asked about, how this module should be reset, to prevent such behavior in the future. Finally I decided for HM-13 module. Module is already implemented and I need to do more tweaking in revision 2 to push next revision. For now module is working on revision 1 prototype board.

Wired communication with PC uses CP2102N UART to Bridge ICs. His cost is lower than FTDI chips and has a lot possible ways to configure it, beginning from drivers, ending at ICs, but soldering it without hot air station is not easy task to do, but it can be done with some patience.

After success of 1st prototype (working!), second was made. On the 2nd prototype everything was moved to the one 2 layers PCB board, with dimension of 4cm x 6cm (I will try to make it even smaller!, but I am concern about EMC problem with it and this could require use 4 layer PCB). Some of components are on the bottom side of the board. 

Checked protocols:
- [x] High Speed CAN
- [x] Medium Speed CAN 
- [x] Single Wire CAN 
- [x] K-LINE
- [x] L-LINE
- [ ] VPW 
- [ ] PWM

Basic connection tested with:
- Fiat Punto MK2 1.2 8V (MultiEcuScan)
- Opel Vectra C 1.8 16V 122KM 
- Citroen DS4 
- Mazda 3 BK 1.6 105KM Z6 2008 (ForScan)

Gallery: https://imgur.com/a/UtiDV

Video: https://youtu.be/GFeOGx49xKc
