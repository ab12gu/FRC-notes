[wiki](https://en.wikipedia.org/wiki/CAN_bus)

- A **controller area network** (**CAN**) is a [vehicle bus](https://en.wikipedia.org/wiki/Vehicle_bus "Vehicle bus") standard designed to enable efficient communication primarily between electronic control units (ECUs)
- We use High Speed CAN
- Andn CAN 2.0B (Extended CAN)

Due to its legacy, CAN 2.0 is the most widely used protocol
- maximum payload size of eight bytes
- typical baud rate of 500 kbit/s

Classical CAN
- includes
	- CAN 2.0A (Standard CAN) and 
	- CAN 2.0B (Extended CAN)
- primarily differs in identifier field lengths
	- CAN 2.0A uses an 11-bit identifier
	- CAN 2.0B employs a 29-bit identifier
		- allows for a greater number of unique message identifiers
		- beneficial in complex systems with many nodes and data types
		- increase in unique message identifiers also increases frame length
			- which in turn reduces the maximum data rate
		- provides finer control over message prioritization 
			- due to more available identifier values
		- CAN 2.0A devices can generally communicate with CAN 2.0B devices, 
			- but not vice versa because of potential errors in handling longer identifiers
- High-speed CAN 2.0 supports bit rates from:
	- 40 kbit/s to 1 Mbit/s 
	- is the basis for higher-layer protocols
- Low-speed CAN 2.0 supports bit rates from:
	- 40 kbit/s to 125 kbit/s 
	- and offers fault tolerance by allowing communication to continue despite a fault in one of the two wires, with each node maintaining its own termination

Two signals, CAN high (CANH) and CAN low (CANL)
- High-speed CAN signaling drives the 
	- CANH wire towards 3.5 V and 
	- CANL wire towards 1.5 V

The CAN bus must be terminated
- The termination resistors are needed to suppress [reflections](https://en.wikipedia.org/wiki/Signal_reflection "Signal reflection") 
- return the bus to its recessive or idle state

High-speed CAN uses a 120 Ω resistor at each end of a linear bus. 
Low-speed CAN uses resistors at each node.

CAN data transmission uses a lossless bitwise arbitration method of contention resolution