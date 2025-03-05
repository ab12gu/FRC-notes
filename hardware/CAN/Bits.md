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

