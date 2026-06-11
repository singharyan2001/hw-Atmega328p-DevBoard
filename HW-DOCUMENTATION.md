# ATMEGA328P Based Hardware Design

**Credits**
Instructor: Piyush Charpe
Course: Arduino compatible Electronics Circuit Design & Eagle PCB Design course using Atmega328p Microcontroller
Platform: Udemy

## Table of Contents


## Overview


## Module 01: Introduction to Electronics Components

### Introduction to Resistors
1. Resistor is a passive two terminal electrical component that implements electrical resistance as a circuit element.
2. It limits the amount of current flowing through the circuit or a branch of a circuit
3. Examples:
    1. To current limit an led, we can connect a resistor in series of x Ohms to limit the intensity of the led.
    2. It is used in voltage divider circuit, can this circuit can be used in opamp where we need to use the voltage divider circuit it provide reference voltage.
4. Resistors are available in both packages - through hole (tht) and surface mount (smd)

### Introduction to Poentiometer
1. A Potentiometer is a three-terminal resistor with a sliding or rotating contact that forms an adjustable voltage divider.
2. A Potentiometer os used as a variable resistor and can be used to set the desired voltage as per the requirement.
3. Its a three terminal device with terminal 1 and 3 (known as outer terminals) are used to connect with the circuit and a fixed value is measured and the 2nd terminal is called the "Wiper Contact" the moves along it.
4. Pinout:
    1. Pin 1 (Input/Ground): Connected to one end of the internal resistive track, and can be wired to ground or a reference voltage depending on the intended direction of adjustment.
    2. Pin 2 (Wiper Contact - Output): The Middle pin, this terminal touches the resistive strip and picks off the adjusted voltage, and this pin alsom connects to the microcontroller or device being controlled.
    3. Pin 3 (Input/Ground): Connected to the opposite end of the resistive track, if Pin 1 is connected to ground, Pin 3 receives the supply voltage (Vin).
5. Applications:
    1. Voltage Divider Circuit with variable output via potentiometer.
    2. Variable Resistor / Rheostat
6. Functional Diagram and Schematic Symbol:
    ![Potentiometer Diagram](imgs/image.png)

### Introduction to Capacitor
1. A Capacitor is a passive two terminal electrical component that stores energy in the form of electric field.
2. Applications of a capacitor - Energy Storage, Filtering.
3. Capacitive reactance (Xc)
4. Resistor provides opposition to current, and capacitive reactance provides opposition to signal or current.
5. The Capacitve reactance of capacitor decided whether the signal will be bypassed or not.
6. In real world, the build of the capacitor consitutes some amount of resistor, inductor and then capacitor.
7. The resistor present in the capacitor is called the Equivalent Series Resistance [ESR] and exhibits the property of resistance.
8. The inductor present in the capacitor is called the Equivalent Series Inductance and exhibts the property of inductance reactance.
9. The Capacitance presents in the capacitor exhibits the property of Capacitive Reactance (Xc).
10. The Combined the effect of ESR, ESL and Xc contributes to the Impedance (Z) of the capacitor.
11. The Impedance of the Capacitor will decide if a signal will be bypassed or not. so if the impedance provided by the capacitor is low, then signal will be bypassed by the capacitor towards the ground. and if high, then signal will not be bypassed.
12. To find out at what frequencies does the capacitor provides what impedance? - The Impedance VS Frequency plot of the Capacitor in the datasheet or manufacturer website.
13. Xc = 1/wc , where w = 2*pi*f --> Xc = 1/2*pi*f*c
14. 