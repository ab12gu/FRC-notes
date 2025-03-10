The roboRIO provides a universal CAN heartbeat 
- any device on the bus can listen and react to. 
- this heartbeat is sent every 20 ms. 
- the heartbeat has a full CAN ID of `0x01011840` 
- (which is the NI Manufacturer ID, RobotController type, Device ID 0 and API ID `0x061`). 
- It is an 8 byte CAN packet with the following bitfield layout

If the `System watchdog` flag is set, motor controllers are enabled
- If 100 ms has passed since this packet was received
	- the robot program can be considered hung
	- and devices should act as if the robot has been disabled

Note that all fields except `Enabled`, `Autonomous mode`, `Test mode`, and `System watchdog` will contain invalid values until an arbitrary time after the Driver Station connects

https://www.playingwithfusion.com/docview.php?docid=1206

Network Throughput
- Extended CAN Frame Structure (up to 128 bits)
	- Data frame identifiers and definitions (39 bits)
	- Data field (up to 64 bits)
	- CRC and End-of-Frame (25 bits)
- 1,000,000 bits / sec / 128 bits = 7800 messages / sec
	- However, some devices want 10 ms notification control loop
		- So it becomes 7800 msg/sec / 100 loops/second = 78 msg/loop

End Resistors
- Bring's CAN back to recessive state
- Absorb any electrical reflections in the network

CAN is a differential bus
- meaning the voltage difference between the “HIGH” and “LOW” lines is what differentiates between zeros and ones
- The network lets only one device speak at a time
- Message priority and collision detection are built into the physical protocol.

![[Pasted image 20250306233038.png]]