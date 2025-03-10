- Message-based protocol designed to allow microcontrollers and devices to communicate with each other’s applications without a host computer. [link](https://docs.wpilib.org/en/stable/docs/software/frc-glossary.html#term-CAN)

Tasks:

1. Research on best practices for diagnosing can bus reliability.
2. Resolve CAN bus reliability. 
	1. We cannot add a wrist until we can reliably operate the EE and Tofs. 
	2. This is an absolute line in the sand. 
	3. Because if we get this wrong it takes down the whole robot.
# Notes

[FRC CAN Device Specifications](https://docs.wpilib.org/en/stable/docs/software/can-devices/can-addressing.html#frc-can-device-specifications "Link to this heading")
- 

[CAN Wiring Basics](https://docs.wpilib.org/en/stable/docs/hardware/hardware-basics/can-wiring-basics.html)
- two wire network
- follow a “daisy-chain” topology
- start at [roboRIO](https://www.ni.com/en-us/shop/model/roborio.html) and go into and out of each device successively until ending at the [PDP](https://docs.wpilib.org/en/stable/docs/software/frc-glossary.html#term-PDP)
- because the CAN network is required to be terminated by 120 resistors and these are built into these two devices
	- PDP ships with the CAN bus terminating resistor jumper in the “ON” position
	- leave the PDP as the end of the bus
	- If you wish to place the PDP in the middle of the bus (utilizing both pairs of PDP CAN terminals) move the jumper to the “OFF” position and place your own 120 terminating resistor at the end of your CAN bus chain.

RoboRIO Connection:
![[roboRioCAN.png]]

CTRE Power Distribution Panel (PDP)
- power distribution module with 8 high-current (40A max)
- 8 lower current (20A / 30A)
- 1 20A protected channel (for [PCM](https://docs.wpilib.org/en/stable/docs/software/frc-glossary.html#term-PCM) and [VRM](https://docs.wpilib.org/en/stable/docs/software/frc-glossary.html#term-VRM))
- 1 10A protected channel (for the roboRIO)
![[PDPCAN.png]]

