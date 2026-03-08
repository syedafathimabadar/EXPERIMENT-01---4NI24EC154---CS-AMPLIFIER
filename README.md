# EXPERIMENT-01---4NI24EC154---CS-AMPLIFIER

Common source Amplifier using NMOS(TMSC180nm) LT-Spice

Project Overview
This project presents the design and simulation of a Common Source (CS) amplifier using an NMOS based on TSMC 180 nm technology in LTspice.

The CS amplifier is one of the most fundamental analog amplifier configurations and is widely used in integrated circuits due to its high voltage gain and simple structure.

DC, AC and TRANSIENT Analysis of CS-Amplifier

CIRCUIT DIAGRAM


<img width="1235" height="902" alt="circuit" src="https://github.com/user-attachments/assets/cfbc0aa6-592f-48d0-abdc-756ce9bd3032" />

The design is implemented using the following specifications:

a.Parameter	Value
b.Supply Voltage = 1.2 V
c.Technology	TSMC 180 nm
d.Channel Length (L)	= 360 nm
e.Load Capacitance (CL)	= 0.5 pF
f. Limit	≤ 0.4 mW

Circuit Description

The circuit consists of:

1.NMOS transistor operating in common source configuration
2.Drain resistor RD
3.Input voltage source Vin
4.Load capacitor CL

The input signal is applied at the gate terminal, while the output is taken from the drain terminal.

The source terminal is connected to ground.

1. Aim 

To design and simulate a Common Source (CS) amplifier using an NMOS transistor in TSMC 180 nm technology using LTspice, and analyze its DC operating point, transient response, and AC frequency response.

Given specifications:

1.Supply Voltage 
VDD = 1.2V

2.Power constraint 
P≤0.4mW

3.Channel Length 
L=360nm

4.Load Capacitance 
CL=0.5pF

The objective is to obtain the voltage gain, bandwidth, and gain-bandwidth product of the amplifier.

Simulation Steps : 

1.Create the schematic in LTspice using NMOS transistor, drain resistor, supply voltage, input source, and ground in common source configuration.

2.Include the TSMC 0.18µm technology library and set the NMOS dimensions appropriately.

3.Perform operating point analysis to obtain DC parameters such as drain current, VGS, and VDS.

4.Run DC sweep analysis by varying the input voltage to observe the transfer characteristics.

5.Perform transient analysis using a sinusoidal input to observe amplification and phase inversion and calculate voltage gain.

6.Conduct AC analysis to study frequency response, gain, and bandwidth.

7.Repeat AC analysis after adding a capacitor and compare the results.

Theory:
A Common Source amplifier provides high voltage gain with phase inversion.

Drain Current (Saturation)
ID = (Kn / 2)(VGS − VT)²
Kn = μn Cox (W/L)

Design Calculations :
1️. Operating Point
Vout = VDD / 2 = 0.6 V

Power constraint: P = VDD × ID ≤ 0.4 mW
ID ≤ 0.4m / 1.2 = 0.3 mA

MOSFET Width Calculation :
To ensure the MOSFET operates in saturation while satisfying the power constraint, the device width (W) is calculated using the saturation current equation.

Saturation Drain Current Equation
ID = (1/2) Kn (VGS − VT)²

Where:
Kn = μn Cox (W / L)

Step 1 — Maximum Drain Current
Given power constraint: P ≤ 0.4 mW

ID ≤ P / VDD
ID ≤ 0.4mW / 1.2V
ID ≤ 0.3 mA

Step 2 — Process Parameters (TSMC 180nm)
Electron mobility (μn) = 273.8 × 10⁻⁴ m²/Vs
Oxide permittivity: εox = ε0 × εr
ε0 = 8.854 × 10⁻¹² F/m
εr = 3.9
Oxide thickness: tox = 4.1 × 10⁻⁹ m
Cox = εox / tox

Step 3 — Kn Expression
Kn = μn Cox (W / L)

Rearranging for W: W = (2 ID L) / (μn Cox (Vov)²)

Where: Vov = (VGS − VT) → Overdrive voltage

Step 4 — Substituting Values
Using:

ID ≈ 0.25–0.3 mA
L = 360 nm
Estimated Vov ≈ 0.2 V
The calculated width: W ≈ 3.3 µm

Final Selected Value
For better bias stability and midpoint operation:

W = 4.5 µm

* Reason for Choosing Larger Width
Improves bias robustness
Ensures saturation across variations
Helps achieve Vout ≈ VDD/2

*Drain Resistor
RD = (VDD − VDS) / ID
RD = (1.2 − 0.6) / 0.3mA = 2kΩ

DC OPERATING POINT

<img width="688" height="331" alt="Operating Point" src="https://github.com/user-attachments/assets/fca37065-69ef-44a0-827a-4e737acf33a3" />

W (µm)	ID	Vout
3.3	0.2 mA	0.778 V
4	0.25 mA	0.695 V
4.5	0.30 mA	0.59 V
Chosen: W = 4.5 µm


Analyses Performed
1. DC Analysis

The DC operating point analysis is used to determine the biasing conditions of the MOSFET in the circuit. It calculates the node voltages and currents when only the DC supply is applied. This analysis helps verify whether the transistor is operating in the saturation region, which is necessary for proper amplification.
​The drain current and output voltage obtained from the simulation confirm that the transistor is correctly biased.

2. AC Analysis

The AC analysis is performed to study the frequency response of the amplifier. A small AC signal is applied at the input, and the output voltage is observed over a range of frequencies.

This analysis helps determine important parameters such as:

1.Voltage gain
2.Cutoff frequency
3.Bandwidth of the amplifier

The gain of the amplifier decreases at higher frequencies due to the presence of internal and load capacitances.

3. Transient Analysis

The transient analysis is used to observe the time-domain behavior of the amplifier when a time-varying input signal is applied.
In this analysis, a sinusoidal input signal is given to the gate of the NMOS transistor, and the output waveform is observed at the drain. The results show that the output signal is amplified and phase inverted, which is the characteristic behavior of a common source amplifier.

The transient analysis also allows calculation of the voltage gain by comparing the input and output peak-to-peak voltages.

1.DC SWEEP ANALYSIS
