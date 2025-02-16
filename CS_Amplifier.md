# Experiment 1: CS Amplifier Characterization in LTspice (180nm Technology)
## Aim
To Simulate a CS amplifier in LTspice to analyze how MOSFET channel length (L) and width (W) impact channel lenght modulation and DC bias, AC gain, and transient response.
## Components Required
N channel MOSFET(nmos4),P channel MOSFET(pmos4), Resistor (1kΩ), DC Power supply of  1.8V,0.9v, Wires.
## Theory
A Common Source (CS) amplifier is a basic MOSFET amplifier configuration used for voltage amplification. It is commonly used in the architecture of analog circuits as minimum with simple construction.A method of operationThe input signal is applied to the gate of the MOSFET.The output across the drain terminal.The source iscommon with GND and geared towards the common threshold for input and output signals.A drain resistor (R1) is used to develop an output voltage.AC signal (V2),applied to the gate, modulates the drain current and gives amplified output.
Relevant observations
1) Voltage gain orientation depends both on the presence of a MOSFET and on resistor values.
2) Change in width of the MOSFETs (W) and channel length (L) affect the gain.
3) Some of the applications are -Audio amplification, Sensor interface,Signal processing,RF circuits.

Equation of drain current for saturation region of operation of MOSFET 

ID = (1/2) * μn * Cox * (W/L) * (VGS - VTH)^2
## DC Analysis
DC analysis means to find the operational point (bias point) MOSFET by calculating some different DC voltages and currents at various nodes of the circuit. For a common source amplifier, we should find the drain current (ID), gate-source voltage (VGS), and check whether the MOSFET is working in cut-off, triode, or saturation regions. It is important to perform the DC analysis since this sets the amplifier for the correct operational bias state before applying an AC signal. In LTspice, the DC analysis is performed using the .op command.
## AC analysis 
AC analysis depicts how the amplifier's gain (𝐴𝑣A v​ ) changes with frequency as it is a critical way of studying the frequency response of the amplifier. It also identifies the bandwidth, the -3dB cutoff frequency, and how the amplifier behaves at different frequencies. AC analysis also assumes that there will be small-signal operation; thus, the MOSFET behavior will have to be linearized around its bias point. AC analysis is done in LTspice using the .ac dec 20 0.1 1T command, which sweeps the frequency from 0.1 Hz to 1 THz.
Ac gain can be calulated using equation Av = -gm *Rd

## Transient analysis
Transient analysis has been performed to track how the output voltage waveform changes over time with the applied AC input signal. This analysis is further employed to see how amplifiers affect the real-time behavior, including signal amplification and the distortions involved. This helps visualize how the circuit responds to different waveforms such as sine waves or pulses. In LTspice, the transient analysis is done by means of the .tran 5 m command to run the simulation for 5 milliseconds and observe a real-time description of the circuit's activity.
## Procedure 

Step 1: Open LTspice and create a New schematic Open LTspice, navigate to file to New Schematic .Save the schematic with an appropriate name.

Step 2:  Place the following components in the schematic-MOSFET (CMOSN or NMOS 180nm technology model)Resistor (R1 = 1kΩ)Voltage sources (V1 for DC supply, V2 for AC input signal)Ground connection (every circuit must have a ground reference).

Step 3: Set Component values DC supply (V1) = 1.8V (connect to drain through R1).AC input source V2 = SINE(0.9 50m 1k) (0.9V DC bias, 50mV AC signal, 1kHz frequency).Resistor (R1) = 1kΩ (between V1 and drain). MOSFET (M1) = 180nm NMOS model (drain connected to R1, source connected to ground, gate connected to V2).
Import MOSFET s(CMOS) datsheet which contains threshold and other specifications of mosfet 
Step 4: Configure simulation click on simulation then edit Simulation Cmd and enter the following:

DC Analysis:  .op to find DC operating point.

AC Analysis: .ac dec 20 0.1 1T to analyze gain and frequency response.

Transient Analysis: .tran 5m to observe the output waveform over time. Place these commands in the schematic.

Step 5: Run SimulationClick Run (green 'Play' button).View results in waveform viewer. Observing DC bias values, gain vs frequency response, and time-domain output waveform.

Step 6: Interpret The results for DC analysis, check VGS, VDS, and ID to confirm the MOSFET is operating. For AC analysis, check the gain plot and bandwidth.Respectively for transient analysis, observe the shape of the output waveform and check that amplification took place.
## Cicuit diagram 
![image](https://github.com/user-attachments/assets/291fa2e6-a13d-4b07-ad03-c733cfa0de56)





