![[framework-diagram.png]]

[FRC Java Tutorial Video](https://www.youtube.com/watch?v=C5DqnIu6g8k)
[Video tutorial docs](https://docs.google.com/document/d/1QAT5izZ8L-tu4IyC9r5SlIA6Q4qgKr19VbmO7vczAfE/edit?tab=t.0)

How code runs:
1. Connect computer via USB
2. Automatically runs `main()` class
3. Automatically calls `startRobot()` [method](https://github.wpilib.org/allwpilib/docs/release/java/edu/wpi/first/wpilibj/RobotBase.html) 
	- starting point for the applications
	- built in class from WPI
1. `Robot` class constructor is the input parameter to `startRobot()` stored as `robotSupplier`
	- it is used as an input constructor
	- robot is started in `startRobot` with command `runRobot(robotSupplier)`
		- new robot object is created
		- `robot.startCompetition()` command is run
			- runs a `while loop` that will have commands run on robot at all times
				- - `TimedRobot` constructor calls `periodic function` 
			- starts `robotInit()`
				- creates new class `RobotContainer()`
					- This is where button bindings are defined :)
