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

1.DC SWEEP ANALYSIS :

<img width="1919" height="444" alt="DC SWEEP" src="https://github.com/user-attachments/assets/010f81d7-8d1c-4387-9d95-7c8f9adf36ed" />

To analyze the DC transfer characteristics of the Common Source (CS) amplifier by sweeping the input voltage and observing the variation in output voltage.

1. Theory

DC Sweep Analysis is used to study how the output voltage or drain current of a MOSFET changes when a DC input parameter is varied. In this analysis, the gate-to-source voltage (VGS) of the MOSFET is swept over a range of values while observing the corresponding change in drain current (ID) or output voltage (Vout).

This helps in understanding the transfer characteristics of the MOSFET. When the gate-to-source voltage exceeds the threshold voltage (VT), the MOSFET starts conducting and the drain current increases.

The drain current in the saturation region is given by:
Id = (1/2) kn (Vov)^2

Where, Vov = Vgs - Vth
kn = μn Cox (W/L)

Thus, DC sweep analysis helps determine the proper biasing point for the MOSFET so that it operates in the saturation region for amplification.

2. Observation

During the DC sweep simulation, the gate voltage (VGS) is gradually increased and the corresponding drain current (ID) and output voltage (Vout) are observed.

From the simulation results:

1.When VGS<VT​, the MOSFET remains OFF and the drain current is nearly zero.
2.When 𝑉𝐺𝑆>𝑉𝑇, the MOSFET begins to conduct and the drain current increases.
3.As VGS, increases further, the drain current increases rapidly and the MOSFET operates in the saturation region.

From the DC sweep graph:

Output voltage remains high at low input voltage.
As input voltage increases beyond threshold voltage, output voltage decreases.
The curve shows the transfer characteristics of the amplifier.

Inference :
The DC sweep confirms:

Proper biasing of the MOSFET
Operation in saturation region
Inverting behavior of the Common Source amplifier
Suitable operating (Q) point for amplification


2.Transient Analysis:

INPUT :

<img width="1917" height="468" alt="INPUT HIGHER" src="https://github.com/user-attachments/assets/9369c7e3-e385-460b-bff4-870d59026ffa" />

<img width="1909" height="441" alt="INPUT LOWER" src="https://github.com/user-attachments/assets/3e5ae6c6-6b28-4500-b430-276cc6dfd7b7" />


Vin(HP) = 909.83mV
Vin(LP) = 909.83mV

Vin(p-p) = 0.0194V

OUTPUT :

 <img width="1916" height="462" alt="OUTPUT HIGHER" src="https://github.com/user-attachments/assets/83575a04-e182-4b7c-aad1-380998107be0" />

 <img width="1910" height="450" alt="OUTPUT LOWER" src="https://github.com/user-attachments/assets/fc3c4996-8c3e-4b61-b9b8-4bb0380ebfba" />

Vout(HP) = 612.59mV
Vout(LP) = 569.39mV

Vout(p-p) = 0.0432V

Gain Obtained:

Av = Vout(p-p) / Vin(p-p) = 2.226
Av(dB) = 20log(2.226) = 6.95dB

Theoretical Gain
Av = gm RD

gm = 2ID / Vov ≈ 2.1 mS
Av ≈ 4.21 → 12.48 dB

Reason for Difference
Channel length modulation
Finite output resistance (ro)
Practical gain ≈ gm(RD || ro)

2. AC Analysis

AC analysis is used to study the frequency response of the amplifier by applying a small AC signal at the input and observing the output voltage over a range of frequencies.

This analysis helps determine:

1.Voltage gain (Av)
2.Cutoff frequency
3.Bandwidth of the amplifier

The gain of the common source amplifier is given by : Av = gm RD

where 𝑔𝑚 is the transconductance and 𝑅𝐷 is the drain resistance.

The negative sign indicates that the output signal is inverted (180° phase shift) with respect to the input. As the frequency increases, the gain decreases due to the effect of parasitic capacitances, which limits the bandwidth of the amplifier.

The frequency response of the Common Source amplifier was analyzed for two loading conditions:

1 fF capacitor (parasitic case)
0.5 pF capacitor (practical load)

Case 1 — With 1 fF Capacitor (Parasitic Case)

<img width="803" height="408" alt="case 1" src="https://github.com/user-attachments/assets/d9306fb9-b95d-4115-8eb5-406f4cf9e143" />

<img width="1246" height="286" alt="case 1 graph" src="https://github.com/user-attachments/assets/d56636ea-8610-4b6b-b7e1-581863c38477" />

Represents near-ideal unloaded output.

Midband Gain ≈ 6 dB
3 dB Bandwidth: fH ≈ 989.7 MHz
Linear Gain
Av = 10^(6/20) = 2

Gain Bandwidth Product
GBP = Av × fH
GBP = 2 × 989.7 MHz
GBP ≈ 1.97 GHz

Unity Gain Bandwidth
UGB ≈ 1.97 GHz

Very high bandwidth due to negligible capacitive loading.

Case 2 — With 0.5 pF Load Capacitor

<img width="644" height="449" alt="case 2" src="https://github.com/user-attachments/assets/1135d627-3a8c-407d-adf0-729b22bc21c1" />

<img width="1227" height="284" alt="case 2 graph" src="https://github.com/user-attachments/assets/f0682b69-e2a8-43ee-92f3-f1534c87bdda" />

Represents realistic output loading.

Gain = 6.87 dB
3 dB Gain = 3.87 dB
Bandwidth: fH = 171.41 MHz
Linear Gain
Av = 10^(6.87/20) = 2.206

Gain Bandwidth Product
GBP = 2.206 × 171.41 MHz
GBP ≈ 378 MHz

Unity Gain Bandwidth
UGB ≈ 0.378 GHz

Bandwidth reduced due to increased capacitive loading.

Observation:

It is observed that when the load capacitance increases, the bandwidth of the amplifier decreases, indicating an inverse relationship between bandwidth and load capacitance.

The Gain–Bandwidth Product (GBP) remains nearly constant for a single-pole MOSFET amplifier, even when the gain or bandwidth changes.

Conclusion:
A Common Source Amplifier was successfully designed using TSMC 180nm NMOS under power constraints.

Key Results:

Gain ≈ 6.8 dB
Bandwidth (with load) ≈ 171 MHz
GBP ≈ 378 MHz
UGB ≈ 0.378 GHz

Inference :

The Common Source MOSFET amplifier designed using TSMC 180 nm technology operates successfully within the given limits of low supply voltage (1.2 V) and restricted power consumption (≤ 0.4 mW). Setting the operating point around 
𝑉𝐷𝐷/2 allows the output signal to swing equally in both directions and keeps the MOSFET in the saturation region, which is essential for stable amplification.

The gain obtained from simulation is slightly lower than the theoretical value. This difference occurs because real MOSFET devices are affected by practical non-ideal effects, such as channel length modulation and limited output resistance, which reduce the overall amplification compared to ideal calculations.

The AC frequency analysis also shows that the bandwidth of the amplifier is highly affected by the load capacitance. When the load capacitance is very small, the circuit is able to operate at very high frequencies. However, when a larger capacitance such as 0.5 pF is connected, the bandwidth decreases significantly. This confirms that an increase in load capacitance leads to a reduction in bandwidth.

Even though the bandwidth changes with capacitance, the Gain-Bandwidth Product (GBP) remains almost constant. This behavior verifies the characteristics of a single-pole amplifier, where the gain and bandwidth adjust inversely to maintain an approximately constant product.

Overall, the experiment highlights important analog design principles, such as proper biasing for maximum signal swing, the effect of device non-idealities on gain, and the influence of capacitive loading on high-frequency performance.

This experiment provides a clear understanding of real-world analog design challenges and validates theoretical concepts through LTspice simulation.

Tools Used
LTspice
TSMC 180nm Model Library
