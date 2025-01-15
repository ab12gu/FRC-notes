`RoboRio`
- Calls `Main.java`
`Main.java`
- Creates instance of `Robot.java` class
`Robot.java`
- Overrides `robotInit` function (run at startup) and:
	- Creates instance of `RobotContainer.java` class
`RobotContainer.java`
- Contains code to separate autonomous & teleop modes
	- Might DELETE
- calls `initializeFeederSubsystem`
	- initializes feeder aka bag motors
- calls `initializeManualInputInterfaces`
	- initializes interfaces aka xbox controls
