# NMOS DC Motor Speed Controller

## Overview
This repository contains the circuit design and simulation for a variable DC motor speed controller using an N-Channel MOSFET. Built and verified in Tinkercad, the circuit demonstrates how an analog voltage divider can manipulate the gate-to-source voltage ($V_{GS}$) of a MOSFET, linearly controlling the drain current to adjust motor RPM.

## Design Access (Tinkercad)
To view, simulate, and grade the circuit design, please access the project via the link below:
* **[Click here to access the Tinkercad Simulation](https://www.tinkercad.com/things/lzl8PzDhsJB/editel?returnTo=%2Fdashboard%2Fdesigns%2Fall&sharecode=5JvMZxhOJ5Z52-phhiRZdKikpimqaiqdXXt9Ygo9eKQ)** 

## Features
*   **Analog Speed Control:** Smooth, variable adjustment of motor RPM via a 10 kΩ potentiometer.
*   **MOSFET Switching:** Utilizes an NMOS transistor operating as a voltage-controlled variable resistor.
*   **Real-time Telemetry:** Integrates multimeter and oscilloscope test points to monitor $V_{GS}$ fluctuations and threshold triggers during operation.

## Components List
*   **Power Supply:** 12V DC
*   **Transistor:** NMOS MOSFET
*   **Actuator:** Standard DC Motor
*   **Potentiometer:** 10 kΩ (Linear)
*   **Resistor:** 200 Ω (Gate protection)
*   **Measurement:** Multimeter & Oscilloscope 

## Circuit Theory
The core of this design relies on the voltage-controlled nature of the NMOS transistor:
1.  **Voltage Divider:** The 10 kΩ potentiometer is connected across the 12V supply and ground. The center wiper outputs a variable control voltage from 0V to 12V.
2.  **Gate Bias ($V_{GS}$):** This variable voltage is fed into the MOSFET's Gate terminal through a 200 Ω resistor, which suppresses high-frequency ringing and limits transient currents charging the gate capacitance. 
3.  **Channel Conduction:** As the potentiometer dial is turned, $V_{GS}$ rises. Once it surpasses the MOSFET's threshold voltage ($V_t$), the drain-to-source channel conducts. Increasing $V_{GS}$ further reduces the channel resistance, allowing more current to flow from the 12V rail, through the DC motor, and into the drain, thereby increasing the motor's speed.

## Simulation & Usage
To interact with the circuit simulation:
1.  Navigate to the Tinkercad Project Link provided above.
2.  Click **Start Simulation** in the top right corner.
3.  Click and drag the dial on the potentiometer. 
4.  Observe the motor's RPM changing dynamically in response to the dial. The attached multimeter provides exact $V_{GS}$ DC readings, while the oscilloscope visualizes the voltage adjustments in real-time.

## Future Hardware Implementation
While this repository focuses on analog Tinkercad simulation, planned physical upgrades to this topology include:
*   **Microcontroller Integration:** Replacing the analog potentiometer divider with an Arduino generating a Pulse Width Modulation (PWM) signal at the gate. This will allow for more efficient, low-heat motor control via duty-cycle adjustments.
*   **Physical Prototyping:** Translating the breadboard schematic into a physical test rig, utilizing Bambu Lab 3D printing to manufacture a custom motor mount and electronics enclosure.
