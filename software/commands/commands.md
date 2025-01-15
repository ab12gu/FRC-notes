[WPI description link](https://docs.wpilib.org/en/stable/docs/software/commandbased/commands.html)

**Commands** represent actions the robot can take
- Commands run when scheduled, until they are interrupted or their end condition is met
- Commands are represented in the command-based library by the `Command` class

Define commands by overriding: 
- `initialize()`
	- called exactly once per time a command is scheduled
- `execute()`
	- runs every 20ms
	- done in the main robot periodic method
- `end()` 
	- called once when the command ends, whether it finishes normally (i.e. `isFinished()` returned true) or
	- it was interrupted (either by another command or by being explicitly canceled)
- `isFinished()`
	- is called repeatedly while the command is scheduled, whenever the scheduler’s `run()` method is called

Command must be able to tell the scheduler when (if ever) it has finished execution
- this is done by overriding the `isFinished()` method
- `isFinished()` is defaulted to return false

### Command Properties

Each `Command` also has three properties, defined by getter methods:

`getRequirements`

`runsWhenDisabled`

`getInterruptionBehaviour`


### Running Actions

The `runOnce` factory, backed by the `InstantCommand` ([Java](https://github.wpilib.org/allwpilib/docs/release/java/edu/wpi/first/wpilibj2/command/InstantCommand.html), [C++](https://github.wpilib.org/allwpilib/docs/release/cpp/classfrc2_1_1_instant_command.html), [`Python`](https://robotpy.readthedocs.io/projects/commands-v2/en/stable/commands2/InstantCommand.html#commands2.InstantCommand "(in RobotPy Commands v2 v2025.1)")) class, creates a command that calls a lambda once, and then finishes


