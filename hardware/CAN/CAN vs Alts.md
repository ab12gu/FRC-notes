- Less electromagnetic interference allowing it to transmit signals faster and more accurately
- Even if the Talon SRX loses power
	- it just acts like a pass-through to the next one, keeping your loop
- if one of the CAN bus wires gets disconnected or shorted or interrupted
	- you will lose all your motors
- FRC uses 1MBit/s and has a maximum recommended stub length of about 1ft. Thus all CANBus leads need to be 1ft or shorter from the start center to the device.
- CANbus has no concept of a “master”; all messages are asynchronously broadcast onto the bus

With the CANivore bus, our star-topology connected devices could not be detected
- After changing them to loop topology (serially connected), the problem resolved and worked well
	- because the bus is run at a higher speed

First Robotics Rate 1Mbit/s
- vs:
	- Automotive: 500 kbps
	- Industrial: 250 kbps
- Benefit by having a higher data throughput by running a higher data bus speed
	- Because it never gets near the 40 meter max for 1Mbit/s (vs others do)

https://www.chiefdelphi.com/t/wire-canbus-for-frc-electronics/416817/4
- WCP canbus lever nuts are good
- ziptie the CAN wire to the power wires to prevent it being pulled out
- cut off the PWM-style Molex ends and substitute a (properly crimped) locking style instead
	- Or lever-nuts
- huge issues with the wagos in the smaller wires
	- zero issues with soldered wires
		- Soldering is viable if you have enough students up to speed on doing it properly, with the tradeoff that repairs and reconfigurations become a lot more difficult
- As long as they are tied down, I’ve never had a wago 221 come loose in both 2018 and 2019. 2020 as well, in practice anyway.
	- If you let them dangle they can work themselves loose.
IDC tee connectors
- No soldering or crimping required and if one fails, you lose a single motor, not half the robot
- issues where the “cover” would pop off or not grab the inside of the wire properly

![[connector4.png]]

- Molex SL, these work fine with a good (expensive Molex) crimper
	- hard time getting the discipline to make good crimps, check for quality, insert into shell and tug test
	
![[connector3.png]]

- Molex Ditto or JST-SM

![[connector2.png]]
![[connector1.png]]

For the sparkmax, REV has cables that introduce jumpers to ensure that it works if disengaged:
- https://www.revrobotics.com/rev-11-1880/

Also cable strengthening through clips:
- https://www.revrobotics.com/rev-11-1229/

![[clip.png]]