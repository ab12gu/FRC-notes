[WPI description link](https://docs.wpilib.org/en/stable/docs/software/commandbased/binding-commands-to-triggers.html)

1. Open file `RobotContainer.java`
2. Class `RobotContainer()` calls class `configureButtonBindings()`
3. Here, define you `trigger/button-command mappings`
	- Triggers can be created via the
	   * {@link Trigger#Trigger(java.util.function.BooleanSupplier)} constructor with an arbitrary predicate, or via the named factories in 
	   * {@link edu.wpi.first.wpilibj2.command.button.CommandGenericHID}'s subclasses for {@link
	   * CommandXboxController Xbox}/{@link edu.wpi.first.wpilibj2.command.button.CommandPS4Controller PS4} controllers or 
	   * {@link edu.wpi.first.wpilibj2.command.button.CommandJoystick Flight joysticks}.