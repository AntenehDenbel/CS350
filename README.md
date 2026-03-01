# CS 350 Emerging Systems Architectures and Technologies Portfolio Artifacts

This repository contains two selected artifacts from the CS 350 course, showcasing my work on interfacing software with hardware components in a Raspberry Pi-based thermostat project. The artifacts demonstrate skills in hardware architecture design, software-hardware integration, and recommending emerging technologies for embedded systems.

## Artifacts

- **Thermostat.py**  
  This Python script implements the core functionality of a thermostat prototype, managing states (off, heat, cool) using a state machine. It interfaces with hardware like LEDs (for visual indicators), buttons (for state cycling and setpoint adjustment), an LCD display (for showing time, temperature, and status), a temperature sensor (AHTx0), and serial communication for status updates. The code handles temperature readings in Fahrenheit, LED pulsing based on comparisons to the setpoint, and periodic server updates.

- **Milestone3.py**  
  This script from Milestone 3 focuses on input handling with buttons and output via LEDs, using a state machine to display Morse code messages ("SOS" or "OK") that toggle on button press. It integrates an LCD display for message status and demonstrates threading for concurrent operations, GPIO management, and event-driven programming.

These artifacts highlight my ability to write maintainable code for cyber-physical systems, analyze hardware impacts on performance (e.g., GPIO timing and I2C bus efficiency), and justify architecture choices (e.g., state machines for reliable state transitions in real-time applications).

## Reflection

### Summarize the project and what problem it was solving.
The project involved prototyping a thermostat system using a Raspberry Pi to simulate heating and cooling controls in a cyber-physical environment. It solved the problem of maintaining a desired room temperature by integrating hardware sensors and actuators with software logic. The system reads temperature data, compares it to a user-set point, and activates visual indicators (LEDs) or states accordingly, while allowing user input via buttons to adjust settings. This addressed key challenges in embedded systems, such as real-time sensor data processing, state management, and hardware-software interfacing, without actual HVAC integration for safety and prototyping purposes.

### What did you do particularly well?
I excelled in implementing state machines to handle complex behaviors reliably, such as cycling through thermostat modes and Morse code transmission in Milestone3.py. The code in Thermostat.py effectively manages concurrent tasks like display updates and serial communication using threading, ensuring smooth operation without blocking. I also handled hardware interactions cleanly, with proper initialization, cleanup, and debugging flags, which made the system robust and easy to test.

### Where could you improve?
I could improve by adding more error handling, such as retries for sensor failures or serial communication issues, to make the system more resilient in real-world scenarios. Additionally, the code could benefit from more modular design, like separating display management into its own module, to enhance reusability. Documentation within the code could be expanded with more inline comments on complex logic, like temperature conversions and pause timings in Morse code.

### What tools and/or resources are you adding to your support network?
I'm adding the `python-statemachine` library for building finite state machines, `gpiozero` for simplified GPIO access, and Adafruit libraries (e.g., `adafruit_ahtx0` for sensors and `adafruit_character_lcd` for displays) to my toolkit. Resources include the Raspberry Pi documentation for hardware specs, Stack Overflow for Python threading best practices, and the course lab guides for circuit building. These will support future IoT and embedded projects.

### What skills from this project will be particularly transferable to other projects and/or course work?
Skills like designing state machines for event-driven systems, interfacing Python with hardware via GPIO and I2C, and managing concurrency with threads are highly transferable to robotics, IoT applications, or any cyber-physical project. Debugging hardware-software interactions and optimizing for real-time performance (e.g., timing LED pulses) will apply to courses in operating systems, networks, or embedded programming. Additionally, justifying architecture choices based on requirements aligns with software engineering principles.

### How did you make this project maintainable, readable, and adaptable?
I used clear class structures (e.g., `ManagedDisplay` and `TemperatureMachine`) to encapsulate functionality, making it easier to modify individual components without affecting the whole system. Descriptive variable names, consistent indentation, and debug flags enhance readability. The code is adaptable through configurable parameters like setpoints and pause durations, and by leveraging libraries that abstract hardware details. Versioning comments in the code headers track changes, supporting long-term maintenance.
