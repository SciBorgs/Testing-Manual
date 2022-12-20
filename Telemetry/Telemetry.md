# Telemetry

## Table of Contents
1. ### [Introduction](#introduction)
    - ### [What is Telemetry?](#what-is-telemetry)
2. ### [Technicals](#technicals)
    - ### [Use Cases of Telemetry](#use-cases-of-telemetry)
        1. #### [Debug Prints](#debug-prints)
        2. #### [Logging](#logging)
3. ### [Procedures](#procedures)

<br/>

# Introduction

## What is Telemetry?
Telemetry involves gathering, sending, and receiving data, which often includes information about how software is functioning. In the context of robotics, telemetry often reports on the current state and/or performance of mechanisms, such as the PID values of a PID controller.

This guide provides documentation for different telemetry tools, rather than explaining how to use them. The documentation includes simple explanations and code examples to help you quickly integrate telemetry into your robot code, depending on your specific use case. It also provides thorough explanations of each tool.

Telemetry has straightforward applications, so there aren't a wide range of use cases. However, the most common use cases for telemetry are helpful for debugging purposes.

<br/>

# Technicals

## Common Use Cases of Telemetry

1. ### Debug Prints
    When you are testing different mechanisms, you may want to print values to the console for debugging purposes, such as values of motors. With the [`Console Viewer`](https://docs.wpilib.org/en/stable/docs/software/vscode-overview/viewing-console-output.html#console-viewer) or [`RioLog`](https://docs.wpilib.org/en/stable/docs/software/vscode-overview/viewing-console-output.html#riolog-vs-code-plugin), both accessable built-in tools, you can easily view console outputs. [Read more about it here](https://docs.wpilib.org/en/stable/docs/software/vscode-overview/viewing-console-output.html#viewing-console-output)
    
    [Console Viewer Window](https://docs.wpilib.org/en/stable/_images/console-viewer-window.webp):
    
    ![console viewer window](https://docs.wpilib.org/en/stable/_images/console-viewer-window.webp)

    [Riolog Window](https://docs.wpilib.org/en/stable/_images/riolog-window.webp):
    
    ![riolog window](https://docs.wpilib.org/en/stable/_images/riolog-window.webp)

    <br/>

2. ### Logging
    Logging is used to track events that occur while a software runs. Logging is beneficial because it’s one way you can debug your program by spotting where errors occur, or finding what went wrong if your program crashes. WPILib logging does on-robot recording of telemetry data, making the implementation of logging super simple. [Read more about implementing logging here](https://docs.wpilib.org/en/stable/docs/software/telemetry/datalog.html)


# Procedures
