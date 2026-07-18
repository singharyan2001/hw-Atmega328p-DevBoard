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
14. Types of Capacitors - Ceramic Capacitors, Tantalum Capacitors, Electrolytic Capacitor, Plastic film, and super capacitor.

---

## Module 2: Intro to Training Hardware & Development Process
Ideal/Primary Hardware Development Process:
```mermaid
graph TD
    %% Sections
    subgraph PLAN[Requiremenrs & Planning Phase]
        PA[Project Acquired]
        PP[Project plan]
    end
    subgraph DESIGN[Design and Development Phase]
        HWARCH[Hardware Architecture<br>Block Diagram]
        SCH[Schematic Design]
        LD[Layout Design]
    end
    subgraph FAB-PROC[Fabrication & Component Procurement]
        PCBMF[PCB Manufacturing]
        BOM[Component Sourcing]
    end
    subgraph ASM-TT[Assembly & Testing]
        PCBA[PCB Assembly]
        PCBTT[PCB Testing and Troubleshooting]
    end
    subgraph FIELD[On-Field Deployment]
        PD[Product Deployment]
    end

    %% Connections
    PA-->PP
    PP-->HWARCH
    HWARCH-->SCH
    SCH-->LD
    LD-->PCBMF
    PCBMF-->BOM
    BOM-->PCBA
    PCBA-->PCBTT
    PCBTT-->PD
```

### Hardware Development Process

#### Plan Phase
##### Project Acquired
Lets is consider two parties - Client and Design Company
1. The Client and Design Company would create and sign an NDA.
2. The Client will share a product requirement document to the Design Company - The Document would contain:
    1. Specifications of the product
    2. Features to incorporate
    3. Product Industry
    4. Quantity of Product
    5. Clients expectation
    6. Deliverty timespan
    7. Project Deliverables
3. The Design Company would then build a proposal for that particular product, which will target the product requirement documentation with inputs from the client.
4. This process will continue between both parties, until they agree on the proposal.

##### Project Plan
Project plan is a product development phase, in whcih the company discusses how to complete a project within a certain time frame considering different stages.
Plan:
1. Project Timeline Creation with mutal team discussion
2. Team roles assignment
3. E.g. An Ideal team:
    1. Hardware Designer
    2. Firmware Developer
    3. Application Developer
    4. mechanical Designer
    5. System Architect (Team lead)
    6. Project Manager

#### Design & Development Phase
This Phase is handled by the Hardware Design Engineer.

#### Hardware Architecture
The hardware block diagram is designed in this phase.

##### Schematic Design
Each block from the hardware block diagram is designed one by one in the schematics of the software.

##### Layout Design
The Layouting of the design blocks is done in this stage, and the PCB Layout and Routing are done by the Hardware Design Engineer.

The Mechanical Engineer would provide inputs and requirements to the hardware design engineer,m so that the pcb can be designed wrt the enclosure design.

#### Fabrication and Procurement Phase
##### PCB Manufacturing
The Hardware Design Engineer would then generate the manufacturing files i.e. Gerber files from the CAD software.
The Gerber files are then shared with the manufacturer to manufacture the PCB.

##### Component Sourcing
This stage is also processed parallely to the PCB Manufacturing phase, and the Bill of Materials (B.O.M) are generated by the CAD Software and Updated with the order quantity requirements.

#### Assembly and Testing Phase
##### PCB Assembly
The Manufactured PCB is received and the team would then solder all the components and get the design ready.
If the Design is complex to solder like BGA or other complex components, the design company may select the PCB-Assembly path, where the manufacturer assembles the PCB and handles the complex sodlering via automated machines and then the entire PCB is assembled or the PCBs are sent to an Electronics Manufacturing Service [EMS] company that would assembly and ready the PCB design and then shipped to the design company.

Note: Whenever the EMS is considered, the cost increases and needs to be taken into considerations by the product manager.

##### PCB Testing and Troubleshooting
The Hardware Design engineer will check all the Blocks in the Design for validating the design is working as intended.

Note: The Hardware may also be keep running for days/Weeks or a month for hardware valdiations.

#### Deployment Phase
##### Product Deployment
The Hardware is then assembled in the enclosure and the firmware is also deployed and tested rigorously and then deployed on field for testing and then released once all the objectives are cleared.

### Hardware Block Diagram Design

```mermaid
graph TD
    %% Blocks
    PSU[Power Supply]
    
    subgraph HOST
        MCU[Microcontroller]
        PROGDBG[Programmer / Debugger Interface]
    end

    subgraph MTRDRV
        MD[Motor Driver]
        MDC[Motor Driver Connector]
    end

    subgraph DISPLAY
        BCD[Binary to BCD Decoder]
        SSD[Seven Segment Display]
    end

    SWI[Switch Input]
    POT[Potentiometer]
    LED[RGB LED]

    %% Connectors
    PSU ==> MCU
    PROGDBG .-> MCU
    
    MCU --> MD
    MD --> MDC

    MCU --> BCD
    BCD --> SSD

    MCU --> SWI & POT & LED
```

## Module 02: Hardware Design & Development

### Power Supply unit [PSU] Design

#### System power budget calculation
Power budget is the power utilization and power consumption calculation associated with the system.

**Power Supply Consumption Table**
| Component         | Voltage   | Current   | Power |
|:------------------|:----------|:----------|:------|
| ATMEGA328P        | 5V        | 300mA     | 1.5W  |
| MTR DRV VCC1      | 5V        | 60mA      | 0.3W  |
| MTR DRV VCC2      | 12V       | 100mA     | 1.2W  |
| BIN2BCD DECODER   | 5V        | 60mA      | 0.3W  |
| Switch Input      | 5V        | 1mA       | 0.005W|
| Potentiometer     | 5V        | 1mA       | 0.005W|
| RGB LED           |           |           |       |
| PSU (5V RAIL)     | 5V        | 422mA     | 2.11W |
| PSU IN (12V RAIL) | 12V       |           |       |

Note:
1. The LDO being used has an efficientcy of 50%.
2. Due to 50% efficientcy, to provide 2.11W at the 5V rail, we would need to provide double the Wattage at the power input side i.e. 2.11*2 = 4.22W. [Input Power: 4.22, Output Power: 2.11W]
3. To Calculate the Input Current needed, we would need to use `P=VI`, therefore `I=P/V` i.e. I=4.22/12 >> 0.351A it.e. 351mA.
4. 351mA is the current requirement for the input current to power the 5V rail, but we also need another 100mA at the output rail to power the Motor Driver section, therefore the total current conumption would br 351+100 = 451mA.
5. Therefore:
    1. `Input Voltage` >> 12V
    2. `Input Current` >> 451mA
    3. `Output voltage@Current` >> 351mA@5V & 12V@100mA.
    4. LDO Efficiency >> 50%

#### Power Supply Design
1. Power Supply IC - 7805 from ST
2. Power Supply Design Components:
    1. Power Input DC Jack with Revere Polarity Protection via schottky Diode.
    2. Input Filtering Capacitor Section
    3. LM708 IC Section
    4. Output Filtering Capacitor Section
    5. PWR Led Indication Section
3. Reverse Polarity Protection Design
    1. General Purpose Diode - Threshold Voltage: 0.7V, therefore for 1A of current -> P = VI, `P = 1(A) * 0.7 = 0.7W` of power dissipation.
    2. Schottky diode - Threshold voltage: 0.3, therefore for 1A of current -> P = VI, `P = 1(A) * 0.3 = 0.3W` of power dissipation.
    3. Therefore the schottky diode has less power consumption, which would then be the better choice in selection.
    4. Three critical parameters to consider when selecting a schottky diode to ensure efficiency, safety, and reliability are `Threshold Voltage`, `Current Rating`, and `Reverse Voltage Rating`.
        1. Threshold Voltage, which is commonly called the forward voltage drop (`Vf`) is the minimum voltage required accross the diode terminals to make it conduct current in the forward direction.
            1. For a standard Schottky diode, this typically ranges from 0.15V to 0.45V, which is significantly lower than the 0.7 V drop of a standard silicon diode.
            2. A lower Vf means lower power dissipation (P = I*Vf) and higher efficiency, maing it ideal for low-voltage or battery-powered applications.
            3. Note: Vf increases as the forward current and operating temperature increases.
        2. Current Rating, which is commonly specified as Average Forward Rectified Current (`If(av)`) is the maximum amount of current the diode can safely conduct continuously in the forward direction without overheating or failing.
            1. This parameter dictates how much load current the diode can handle under normal operating conditions.
            2. Selecting a diode with a current rating at least 20% to 50% higher than your circuit's peak continuous operating current to provide a safety margin.
            3. Also check the Peak Surge Current (`Ifsm`) if the circuit experiences brief, massive current spikes during startup.
        3. Reverse Voltage Rating, which is commonly specified as Peak Repetitve Reverse Voltage (`Vrrm`) is the maximum voltage the diode can withstand when it is reverse-biased (blocking current) before it breaks down.
            1. If the voltage in reverse exceeds this limit, the diode will enter avalanche breakdown, conduct heavily in reverse and likely destroy itself.
            2. Choose a diode where Vrmm is atlease 1.5 to 2 times higher than the maximum voltage expected in your circuit.
            3. This buffer protects the diode from inductive voltage spikes and ringing.
            4. Note: Schottky diode inherently have higher reverse leakage currents than standard silicon diodes, and this leakage increases drastically at high temperatures.
    5. Diode selected for  the circuit: SS14
4. Input & Output Filtering Capacitor Section
    1. Local Capacitor - to fullfil the sudden current requirement by the circuit at startup.
    2. The Local Capacitors are connected at both the input and output section of the LM708 IC.
    3. Lower ESR will allow fast charging of the capacitor.
    4. A lower ESR capacitor like 0.1 uf at input and output to allow the capacitor to charge faster, but also filter high frequency noise on the DC Line.
    5. The Bypass Capacitor (0.1 uf) is integrated at input and output sections to filter out higher frequency and also lower the ESR for fast charging of the capacitors.
5.  PWR Led Indication Section
    1. Forward Voltage (Vf)
    2. Maximum current (Imax)

### Microcontroller Design
1. MCU Deepdive - understood datasheet sections, peripherals, and pinouts.
2. MCU Vcc and AVcc Filtering and Bulk Capacitor considerations
3. MCU Reset Switch design
4. MCU Debug/Programmer interface design
5. MCU external oscillator design



### Motor Driver Design
1. L298D Driver IC - understood pinout of the IC, pin connections of motor with driver, and flyback diodes application with motors and drivers.
2. L293D Driver IC Pinouts
    1. VCC1 -> 5V
    2. VCC2 -> 4.5V to 36V
    3. 4 * GND
    4. 1,2 EN -> PWM Pin for Motor A
    5. 1A -> DIR 1 Pin for Motor A
    6. 1Y -> Output Terminal 1 for Motor A
    7. 2Y -> Output Terminal 2 for Motor A
    8. 2A -> DIR 2 Pin for Motor A
    9. 4A -> DIR 4 Pin for Motor B
    10. 4Y -> Output Terminal 1 for Motor B
    11. 3Y -> Output Terminal 2 for Motor B
    12. 3A -> DIR 3 Pin for Motor B
    13. 3,4 EN -> PWM Pin for Motor B
3. The L293D is a Dual H-Bridge Motor Driver.
    1. Note - The "D" in L293D is extremely important - it stands for built-in Darlington arrays with internal flyback diodes.
    2. When a spinning motor is suddenly switched off, its collapsing magnetic firld kicks back a massive, high voltage spike of reverse current.
    3. The "D" version has internal clamp diodes that catch this spike and dump it safely into the power rail, protecting your logic circuit.
4. L293D Driver Control [Example: Motor A Side]
    1. `VCC1` is the Logic Voltage
    2. `VCC2` is the Motor Voltage
    3. `1,2 EN` is the Enable pin, Think of this as the "Throttle".
    4. `1A` & `2A` are the Input pins, Think of these as the "Steering Wheel", connected to standard MCU GPIO Pins.
    5. `1Y` & `2Y` are the Output pins, Connect them directly to the wires of the DC Motor.
    6. `GND` is the Sytem Ground.
    7. Note: The Four Ground Pins sit in the center of the IC, they act as primitive thermal heatsink, they are ment to be soldered to a wide copper pour on the PCB to wick heat away from the silicon.
5. The Logic Truth Table to move Motor A
    | `1,2 EN` (Throttle)   | `1A` (Steering 1) | `2A` (Steering 2) | Physical Motor Output |
    |:----------------------|:------------------|:------------------|:----------------------|
    | PWM                   | HIGH              | LOW               | SPIN FORWARD DIRECTION|
    | PWM                   | LOW               | HIGH              | SPIN REVERSE DIRECTION|
    | HIGH                  | HIGH              | HIGH              | ACTIVE BRAKE          |
    | HIGH                  | LOW               | LOW               | ACTIVE BRAKE          |
    | LOW                   | X                 | X                 | COAST [HIGH-Z]        |


### Seven Segment Display Design
1. Seven Segment Display
    1. A 7-segment display is an electronic component used to display numbers (and some basic letters) using seven individual light-emitting segments arranged in a figure-8 pattern.
    2. It can be driven via microcontroller's GPIO pins or via a driver IC interface like CD4511BE.
    3. There are two main electrical configurations for 7-segment displays. They look identical on the outside but wire up completely differently:
        1. Common Cathode (CC): All the negative terminals (cathodes) of the LEDs are tied together to ground. You turn a segment ON by sending a HIGH voltage (logic 1) to its pin.
        2. Common Anode (CA): All the positive terminals (anodes) of the LEDs are tied together to VCC (power). You turn a segment ON by pulling its pin LOW to ground (logic 0).
    4. Most single-digit 7-segment displays have 10 pins (5 on the top, 5 on the bottom).
        1. Common Pins: The middle pin on both the top and bottom rows connects to the common terminal (either Ground for CC or Power for CA).
        2. Segment Pins: The remaining 8 pins connect directly to the individual segments (a through g and DP).
    5. To display a specific number, you must light up a specific combination of segments. Here is the logic for a Common Cathode display:
        |Digit  | a | b | c | d | e | f | g |
        |:------|:--|:--|:--|:--|:--|:--|:--|
        | 0     | 1 | 1 | 1 | 1 | 1 | 1 | 0 |
        | 1     | 0 | 1 | 1 | 0 | 0 | 0 | 0 |
        | 2     | 1 | 1 | 0 | 1 | 1 | 0 | 1 |
        | 3     | 1 | 1 | 1 | 1 | 0 | 0 | 1 |
        | 4     | 0 | 1 | 1 | 0 | 0 | 1 | 1 |
        | 5     | 1 | 0 | 1 | 1 | 0 | 1 | 1 |
        | 6     | 1 | 0 | 1 | 1 | 1 | 1 | 1 |
        | 7     | 1 | 1 | 1 | 0 | 0 | 0 | 0 |
        | 8     | 1 | 1 | 1 | 1 | 1 | 1 | 1 |
        | 9     | 1 | 1 | 1 | 1 | 0 | 1 | 1 |
    6. Critical Hardware Requirement
        1. Current-Limiting Resistors: You must place a resistor (typically 220Ω to 470Ω) in series with each individual segment pin.
        2. Warning: Connecting the common pin directly to power/ground without resistors on the segments will burn out the LEDs instantly.
2. Seven Segment Display Driver IC - CD4511BE [BCD to Seven Segement Driver IC]
    1. The CD4511BE is a popular CMOS Binary Coded Decimal (BCD) to 7-Segment Latch/Decoder/Driver integrated circuit.
    2. It is a popular CMOS Binary Coded Decimal (BCD) to 7-Segment Latch/Decoder/Driver integrated circuit. It is primarily used to take a 4-bit digital binary input and translate it into the signals required to control and illuminate a numeric 7-segment LED display directly.
    3. Key Technical Specifications:
        1. Logic Family: 4000 CMOS
        2. Operating Voltage Range: Wide supply range from 3V to 18V.
        3. Output Sourcing Current: Up to 25 mA per segment, allowing it to directly drive LEDs without external buffer transistors.
        4. Compatible Display Type: Exclusively designed for Common Cathode 7-segment displays.
        5. Operating Temperature: Military-grade resilience ranging from -55°C to +125°C.
    4. Functional Core Blocks: The IC combines three major electronic components into a single monolithic package:
        1. 4-Bit Storage Latch: Holds and retains the BCD input data so that the display remains stable even if the central processor changes tasks or multiplexes data.
        2. BCD-to-7-Segment Decoder: Decodes standard 8421 binary values (0000 through 1001) into appropriate individual alphanumeric segment activations (a through g).
        3. NPN Bipolar Output Drivers: Integrated high-current output components that physically source the electricity needed to light up the display segments safely.
    5. CD4511BE Pinout:
        1. 4 standard inputs (A, B, C, D)
        2. 7 Segment outputs a to g.
        3. Lamp Test (LT): Overrides all data inputs to light up every display segment at once. This lets you quickly check for dead display segments.
        4. Blanking Input (BL): Instantly turns off or pulse-modulates all segments. It is commonly used for energy saving or regulating display brightness.
        5. Latch Enable (LE / Strobe): When toggled, it locks in the current input value so the display freezes on that specific number while the input signals change.
3. Circuit Understanding for Schematics

### Switch, Preset, & RGB Led Designs
1. Input Switch design is resued from the reset switch design
2. Preset design is basically potentiometer design which is used to simulate an analog sensor.
3. RGB led being used is 3 control signal type rgb led, with no host controller. its different from the WS2812b led.

## Module 03: PCB Layout Design & Development
1. Module 03 contents: PCB Stackup, DXF file, and Component placement planning, placement, layout design, and Intro to ULP.
