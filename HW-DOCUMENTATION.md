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

![Potentiometer Diagram](imgs/image.png)

