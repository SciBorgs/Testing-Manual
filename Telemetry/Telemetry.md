# Telemetry

## Table of Contents
1. ### [Introduction](#introduction)
    - ### [What is Telemetry?](#what-is-telemetry)
2. ### [Technicals](#technicals)
    - ### [Common Use Cases of Telemetry in Robotics](#common-use-cases-of-telemetry-in-robotics)
        1. #### [Print Debugging](#print-debugging)
        2. #### [Logging](#logging)
        3. #### [Dashboard](#dashboard)
3. ### [Procedures](#procedures)

# Introduction

## What is Telemetry?
- Telemetry involves gathering, sending, and receiving data, which often includes information about how software is functioning. In the context of robotics, telemetry often reports on the current state and/or performance of mechanisms, such as the PID values of a PID controller.

- This guide provides documentation for different telemetry tools, rather than explaining how to use them. The documentation includes simple explanations and code examples to help you quickly integrate telemetry into your robot code, depending on your specific use case. It also provides thorough explanations of each tool.

- Telemetry has straightforward applications, so there aren't a wide range of use cases. However, the most common use cases for telemetry are helpful for debugging purposes.

# Technicals

## Common Use Cases of Telemetry in Robotics

1. ### Print Debugging 
    - When you are testing different mechanisms, you may want to print values to the console for debugging purposes, such as values of motors. With the [`Console Viewer`](https://docs.wpilib.org/en/stable/docs/software/vscode-overview/viewing-console-output.html#console-viewer) or [`RioLog`](https://docs.wpilib.org/en/stable/docs/software/vscode-overview/viewing-console-output.html#riolog-vs-code-plugin), both accessable built-in tools, you can easily view console outputs such as your debug prints. In addition, these consoles also provide helpful information such as when the robot program starts and more. [Read more about how to set up these tools here.](https://docs.wpilib.org/en/stable/docs/software/vscode-overview/viewing-console-output.html#viewing-console-output)
    
    - If you are interested, [here are some extra information about debugging in general](https://frc-pdr.readthedocs.io/en/latest/GoodPractices/debugging.html#loggers)
    
    - [Console Viewer Window](https://docs.wpilib.org/en/stable/_images/console-viewer-window.webp):
    
    ![console viewer window](https://docs.wpilib.org/en/stable/_images/console-viewer-window.webp)

    - [Riolog Window](https://docs.wpilib.org/en/stable/_images/riolog-window.webp):
    
    ![riolog window](https://docs.wpilib.org/en/stable/_images/riolog-window.webp)

2. ### Logging
    - Logging is used to track events that occur while a software runs. Logging is beneficial because it’s one way you can debug your program by spotting when and where errors occur, or having the capability to find what went wrong if your program crashes. Luckily, WPILib logging supports on-robot recording of telemetry data, making implementations of logging super simple. [WPILib's documentation](https://docs.wpilib.org/en/stable/docs/software/telemetry/datalog.html) provides a detailed explanation about data logging, but if you want to implement logging into your code, here are the important sections:
        * [Standard Data Logging using DataLogManager](https://docs.wpilib.org/en/stable/docs/software/telemetry/datalog.html#standard-data-logging-using-datalogmanager)
        * [Logging Joystick Data](https://docs.wpilib.org/en/stable/docs/software/telemetry/datalog.html#logging-joystick-data)
        * [Downloading Data Logs from the Robot](https://docs.wpilib.org/en/stable/docs/software/telemetry/datalog.html#downloading-data-logs-from-the-robot) (It is advisable to read all the sections under this heading, as it details how to export log files to be analyzed)
        ![datalog tool](https://docs.wpilib.org/en/stable/_images/csv-export-1100.webp)
    
    - If you would like to have custom data logging, WPILib also supports this. [Read more about it here.](https://docs.wpilib.org/en/stable/docs/software/telemetry/datalog.html#custom-data-logging-using-datalog)
    
    - FRC Driver Station has the ability to create log files of important diagnostic data while running, which can be reviewed later using the FRC Driver Station Log Viewer. [Read more about utilizing this tool here](https://docs.wpilib.org/en/stable/docs/software/driverstation/driver-station-log-viewer.html)
    ![logfileviewer](https://docs.wpilib.org/en/stable/_images/logviewer.webp)
    ![logging thing](https://docs.wpilib.org/en/stable/_images/eventlist.webp)

    - The `Shuffleboard` dashboard (which will be discussed later) supports the logging of widget updates. [Read more about how to use it here.](https://docs.wpilib.org/en/stable/docs/software/dashboards/shuffleboard/getting-started/shuffleboard-recording.html#recording-and-playback)
    ![shuffleboard log viewer](https://docs.wpilib.org/en/stable/_images/playback1.webp)
    
3. ### Dashboards
    - To simply explain WPILib dashboards, let's use a simple example of a real-world dashboard. The dashboard of a car contains widgets such as an odometer, a coolant and engine oil temperature gauge, a fuel level gauge, dashboard lights that each represent different important information. A WPILib dashboard functions similarly to this.

# Procedures
