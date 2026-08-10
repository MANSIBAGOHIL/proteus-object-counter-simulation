# proteus-object-counter-simulation
Proteus simulation of an expandable digital object counter using a 555 timer, CD4518 BCD counter, CD4511 display driver, and seven-segment display.

# Versatile Object Counter

A Proteus-based digital electronics simulation that counts object-detection events and displays the current count on a seven-segment display. The design combines a 555 timer, CD4518 BCD counter, CD4511 BCD-to-seven-segment driver, and supporting logic.

> This repository preserves an academic simulation project from 2022. The original editable Proteus project file is not currently available, so the repository contains the circuit images, and demonstration media that remain from the project.

## Technologies and Components

- Proteus Design Suite
- NE555 timer IC
- CD4518 dual BCD up-counter
- CD4511 BCD-to-seven-segment latch/decoder/driver
- Seven-segment display
- AND gate
- NPN transistor
- 470 Ω and 330 kΩ resistors
- 0.01 µF and 1 µF capacitors

## Features

- Counts input events and shows the result on a seven-segment display
- Uses a monostable 555 timer to produce a stable clock pulse
- Converts the CD4518 BCD output into display-segment signals through the CD4511
- Supports an expansion concept for increasing the available count range
- Uses a push button in the Proteus simulation as a substitute for the physical IR sensor/phototransistor input

## How It Works

In the intended physical design, an object interrupts an infrared beam between a transmitter and phototransistor. That change drives an NPN transistor and triggers the NE555 timer.

The NE555 is configured as a monostable multivibrator and generates a pulse of approximately 330 ms. That pulse clocks the CD4518 counter. The counter produces a BCD value, and the CD4511 converts that value into the segment signals required by the seven-segment display.

For the Proteus demonstration, we replaced the phototransistor input with a push button so that each simulated object-detection event could be triggered manually.

## Simulation Process

1. We studied the NE555 timer, CD4518 counter, and BCD-to-seven-segment conversion stage.
2. We recreated the counter circuit in Proteus.
3. We substituted a push button for the unavailable phototransistor model/input during simulation.
4. We configured the NE555 as a monostable pulse generator.
5. We connected the timer output to the CD4518 clock input.
6. We used the CD4511 instead of the 74LS47 from the reference circuit because the CD4511 produced the required simulated output with the selected display arrangement.
7. We triggered the input and observed the displayed count increase.

## Viewing the Demonstration

The simulation cannot currently be rerun from this repository because the original editable Proteus project file is unavailable.

- Watch the demonstration: [`demo/versatile-object-counter-demo.mp4`](demo/versatile-object-counter-demo.mp4)
- View the simulated circuit: [`images/circuit-diagram.png`](images/circuit-diagram.png)

## What We Learned

- How a monostable 555 timer can condition an input into a clock pulse
- How a BCD counter represents decimal counts
- How a BCD-to-seven-segment driver controls a numeric display
- How to substitute a simulation input when a required physical component is unavailable
- How component substitutions can affect circuit and display compatibility
- How a counter design can be expanded to support additional digits

## Limitations and Possible Improvements

- Recover or recreate the editable Proteus project file
- Document the exact Proteus version and simulation settings
- Add a verified pin-to-pin wiring table
- Reintroduce and test an IR transmitter/phototransistor stage
- Build and test the circuit with physical components
- Add a reset control and demonstrate multi-digit expansion
- Explain and verify the rollover/reset logic at a count of nine

## Contributors

- Mansiba Gohil
