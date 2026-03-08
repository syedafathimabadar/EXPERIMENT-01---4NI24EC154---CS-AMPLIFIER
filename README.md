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



