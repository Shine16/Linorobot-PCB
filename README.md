# Linorobot PCB

![pcb.PNG](https://github.com/Shine16/Linorobot-PCB/blob/master/assets/pcb.PNG?raw=true)

![schematic.png](https://github.com/Shine16/Linorobot-PCB/blob/master/assets/schematic.png?raw=true)

## Main Circuit

Circuit was designed based on the Linorobot circuit found [here](https://github.com/linorobot/linorobot/wiki/2.-Base-Controller).

Main components such as controller, IMU, motor driver are attached by 2.54mm pin female connectors on the PCB for modularity, and to aid future maintenance, able to be swapped out as required.

Main edit was to use a [TB6612FNG](https://www.aliexpress.com/wholesale?catId=0&initiative_id=SB_20190813133730&SearchText=TB6612FNG) for the motor driver, it was chosen as it could output an adequate average of 1.2A for two DC motors, and small footprint fit the PCB well. It was estimated that each DC motor would draw 3-500mA.

![linorobot_2wdrev2_bb](https://github.com/linorobot/lino_docs/raw/master/schematics/v2/linorobot_2wdrev2_bb.png)

## Battery power

Plan was to use a [12v 6800mAH](https://www.aliexpress.com/item/32836166839.html) Li-ion pack as it was the most value for money. The pack has an onboard over-discharge, short protection and regulates charging to all cells by a single plug connector! Connection from battery to the PCB would be by a 5.5x2.1mm barrel plug connector which was designed in.



## Onboard DC-DC

The Linorobot control will use at max approximately 2.5A, a 5v DC-DC was designed onboard the PCB. A copper cutout for the Inductor was done reduce on noise induced.

The DC-DC circuit was designed based on the [AIC2510-50GM5TR](https://datasheet.lcsc.com/szlcsc/Analog-Integrations-AIC2510-50GM5TR_C211625.pdf) datasheet, with values selected for fixed a 5v configuration.



## Motor Connections

For connections to the two DC encoder motors, spring clamp terminal blocks were used. The PCB will not require a screwdriver or soldering to connect motor wires!

![springClamp.PNG](https://github.com/Shine16/Linorobot-PCB/blob/master/assets/springClamp.PNG?raw=true)


## Future development  - SPI node

The Teensy 3.2 requires a USB cable to the RPI. As a possibility to save on one USB cable, a ROS SPI node will be required, and some development to Teensy firmware. SPI connection was designed in between RPI and Teensy to be used later.