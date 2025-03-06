[WPILib description link](https://docs.wpilib.org/en/stable/docs/software/roborio-info/roborio-introduction.html)

![[roboRio.png|300]]

The roboRIO has a basic architecture of a Real-Time processors + FPGA (field programmable gate array)
- reconfigurable robotics controller that includes built-in ports for 
	- inter-integrated circuits (I2C)
	- serial peripheral interfaces (SPI)
	- RS232
	- USB
	- Ethernet
	- pulse width modulation (PWM)
	- relays to quickly 
- to connect the common sensors and actuators used in robotics

Controller features:
- LEDs, buttons, an onboard accelerometer, and a custom electronics port
- Onboard dual-core ARM real-time Cortex‑A9 processor and customizable Xilinx FPGA.

[Specs](https://www.ni.com/docs/en-US/bundle/roborio-frc-specs/page/specs.html)

Processor:
- Xilinx Z-7020 All Programmable SoC dual-core ARM Cortex-A9
- Speed: 667 MHz
- Cores: 2

Memory:
- Nonvolatile: 512 MB
- DDR3 (Ram, _SDRAM_)
	- Memory: 256 MB
	- Clock Frequency: 533 MHz
	- Data Bus Width: 16 bits

FPGA: Xilinx Z-7020

Network:
- Network Interface: 10BaseT and 100BaseTX Ethernet
- Compatibility: IEEE 802.3
- Communication Rates: 10 Mbps, 100 Mbps, auto-negotiated
- Max cabling distance: 100 m/segment