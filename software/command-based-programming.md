[WPILib Description Link](https://docs.wpilib.org/en/stable/docs/software/commandbased/what-is-command-based.html)

The command-based paradigm is also an example of [declarative programming](https://docs.wpilib.org/en/stable/docs/software/frc-glossary.html#term-declarative-programming)
- A style of software which focuses on describing _what_ a program should do, rather than _how_ it gets done

A user can specify that “the robot should perform an action when a condition is true” (note the use of a [lambda](https://docs.wpilib.org/en/stable/docs/software/commandbased/index.html#lambda-expressions-java)):

```new Trigger(condition::get).onTrue(Commands.runOnce(() -> piston.set(DoubleSolenoid.Value.kForward))); ```

In contrast, without using command-based, the user would need to check the button state every iteration, and perform the appropriate action based on the state of the button.

![[command-cloud.png]]

The command-based pattern is based around two core abstractions: **commands**, and **subsystems.**
- only one command can use a given subsystem at the same time.
- subsystems allow users to “hide” the internal complexity of their actual hardware from the rest of their code

Commands are run by the `CommandScheduler` singleton, which polls triggers (such as buttons) for commands to schedule, preventing resource conflicts, and executing scheduled commands

The scheduler’s `run()` method must be called; it is generally recommended to call it from the `robotPeriodic()` method of the `Robot` class, which is run at a default frequency of 50Hz (once every 20ms)

Multiple commands can run concurrently, as long as they do not require the same resources on the robot.
- commands specify which subsystems they interact with
- scheduler will ensure that no more more than one command requiring a given subsystem is scheduled at a time


