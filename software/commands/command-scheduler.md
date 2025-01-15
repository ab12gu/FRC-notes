[WPILib Description Link](https://docs.wpilib.org/en/stable/docs/software/commandbased/command-scheduler.html)

The `CommandScheduler` is the class responsible for actually running commands

Each iteration
- ordinarily once per 20ms
- the scheduler polls all registered buttons
- schedules commands for execution accordingly
- runs the command bodies of all scheduled commands
- ends those commands that have finished or are interrupted
---

The `CommandScheduler` also runs the `periodic()` method of each registered `Subsystem`

The `CommandScheduler` is a _singleton_, meaning that it has only one instance
- To access the scheduler, users must call the `CommandScheduler.getInstance()` command.
- To run scheduler, users _must_ call `CommandScheduler.getInstance().run()` from the `robotPeriodic()` method of their `Robot` class

To schedule a command, users call the `schedule()` method
- This method takes a command, and attempts to add it to list of currently-running commands
- If it is added, its `initialize()` method is called
	1. Verifies that the command isn’t in a composition.
	2. [No-op](https://docs.wpilib.org/en/stable/docs/software/frc-glossary.html#term-no-op) if scheduler is disabled, command is already scheduled, or robot is disabled and command doesn’t [runsWhenDisabled](https://docs.wpilib.org/en/stable/docs/software/commandbased/commands.html#runswhendisabled).
	3. If requirements are in use:
	    - If all conflicting commands are interruptible, cancel them.
	    - If not, don’t schedule the new command.
	4. Call `initialize()`

The `initialize()` method of each `Command` is called when the command is scheduled, which is not necessarily when the scheduler runs (unless that command is bound to a button).

**What does a single iteration of the scheduler’s `run()` method actually do?**
1. the scheduler runs the `periodic()` method of each registered `Subsystem`
2. the scheduler polls the state of all registered triggers to see if any new commands that have been bound to those triggers should be scheduled. Then runs its `Initialize()` method
3. the scheduler calls the `execute()` method of each currently-scheduled command, and then checks whether the command has finished by calling the `isFinished()` method. If the command has finished, the `end()` method is also called, and the command is de-scheduled and its required subsystems are freed
4. Finally, any registered `Subsystem` has its default command scheduled (if it has one). Note that the `initialize()` method of the default command will be called at this time.


The scheduler can be disabled by calling `CommandScheduler.getInstance().disable()`. When disabled, the scheduler’s `schedule()` and `run()` commands will not do anything.



