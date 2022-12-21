# Table of Contents
- [Introduction](#introduction)
- [Using SysID](#using-sysid)
- [Using SysID (General Mechanism)](#using-sysid-general-mechanism)
- [Using SysID (Drivetrain)](#using-sysid-drivetrain)
- [Helpful links](#helpful-links)

# Introduction

SysID is a built in feature in wpilib that allows us to effectively generate and tune [PID](insert link when made) and [SVA](insert link when made) values.

# Using SysID

1. Open SysID by typing SysID into the your search bar
2. Go to the generator tab and put your team number under team/IP

There are different modes for different mechanisms. For now, we will only focus on [Drivetrain](#using-sysid-drivetrain) and [General Mechanism](#using-sysid-general-mechanism) sysID.

# Using SysID (General Mechanism)

3. As of 2022/2023 (necessary?), for the motor controller section, set the motor controller to Spark Max (Brushless). Make sure to set motors to inverted when applicable!
4. For the CAN ID, enter the ID found on the Spark Max connected to the motor of the mechanism you are testing. If there are multiple motors, press the plus to add more.
5. In the encoder section, enter the encoder port (unless you are using CanCoders)
6. Under encoder parameters, set the gearing to whatever the gear ratio is for the mechanism. For counts per revolution set it to the value 8192 if you are using throughbores, or 1 if you are using integrated Neo encoders. If you are using another encoder, look up its counts per revolution.
7. Under logger go to project parameters. For mechanism, set it to the mechanism you are using. For example, hopper is elevator intake and flywheel is under simple
8. For unit type use whatever unit you are using and set units per rotation. Use rotation only if the mechanism is 1 to 1. Elsewise use whatever unit that you have associated to this mechanism like meters when running sysID on Drivetrain or angular measurements such as degrees or radians for your turret or hood.

 (FLAG: WHAT DO YOU USE OTHERWISE?)


9. The Voltage Parameters represent the voltage applied during tests. To set the parameter, slide the slider to whatever voltage ramp rate you want. For precise or very breakable mechanisms set both quasistatic and dynamic step voltage to low values. Low Voltage also tends to be more accurate.
10. To test on the robot, use an ethernet cable to attach the robot to the laptop from which you will deploy the sysID code. Set logger mode to enabled, then click apply. If NT Connected is shown to the right of it click deploy under team/ip in generator. You will then choose a save location on your computer ideally in the sysID folder in the cloned respository. Now run all your tests once you have finished all your tests you now should click save and now you have your data.

 (FLAG: ADD SOME PUNCTUATION I CAN'T READ THIS)
 
11. To analyze your data go to analyzer, select the sysID data from the folder you stored it in, run the analyzer and get the Feedback and Feedforward analysis. Note that Feedback will yield PID values and Feedforward will yield SVA values.
12. You now have PID and SVA values!

# Using SysID (Drivetrain)

3. In loggers go to motor controllers. Set your motor controllers to Spark Max Brushless and choose which side of motors are inverted and for encoders use the encoder we are using whether it be CanCoders, Integrated Neos or whatever. Assuming we use swerve with CanCoders Invert one side of the cancoders
5. For Gyro set the gyro to pigeon get the CAN ID and as of 2022/2023 we do not have talons
6. Encoder Parameters, the counts per revolution on a CanCoder is 4096 Counts Per Revolution and Gearing is just the gear ratio of where the encoder is mounted
7. Go to Logger and project parameters have mechanism as Drivetrain and Unit Type as meters and set the Units Per Rotation as the circumfrence of the wheel
8. Set up your voltage parameters. Lower values are more precise, values but don't be afraid to choose high values as long as you have a lot of space
9. Follow steps 10-12 from [Using SysID (General Mechanism)](#using-sysid-general-mechanism)

# Helpful links

1. [WPILib SysID docs](https://docs.wpilib.org/en/stable/docs/software/pathplanning/system-identification/index.html)

