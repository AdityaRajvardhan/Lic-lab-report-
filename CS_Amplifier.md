# Experiment 1: CS Amplifier Characterization in LTspice (180nm Technology)
## Aim
To Simulate a CS amplifier in LTspice to analyze how MOSFET channel length (L) and width (W) impact channel lenght modulation and DC bias, AC gain, and transient response.
## Components Required
N channel MOSFET(nmos4),P channel MOSFET(pmos4), Resistor (1kΩ), DC Power supply of  1.8V,0.6v, Wires.
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
![WhatsApp Image 2025-02-17 at 20 46 47_55ddfa41](https://github.com/user-attachments/assets/6c378108-4265-4867-968f-ebf6dddb8aa2)

## Calculation




P = VDD * ID

ID = P/VDD

ID = 50μW / 1.8V
ID = 27.7μA
Channel Length (L) = 180nm.

Supply Voltage (Vdd) = 1.8V.

Gate Voltage (Vg) = 0.6V.

Power Budget = 50μW.

Drain Current (Id) = 27.7μA.

## Results
### DC Anaylsis 

![WhatsApp Image 2025-02-17 at 23 19 46_6860a384](https://github.com/user-attachments/assets/09644bba-88c7-4fde-a0d3-acd88e8e152d)

Id=27.7uA
Vout=1.772V
Width=1.018u
DC Operating point : (1.772V,27.7uA ) is obtained for 1.018um Width and 180nm Length.
###  AC anaylsis
![WhatsApp Image 2025-02-17 at 23 50 12_e50229db](https://github.com/user-attachments/assets/591e551a-4e3c-41a5-b350-f5130c6759c4)


Gain= -3db

### Transient Anaylsis
![image](https://github.com/user-attachments/assets/38ca7b3d-96d3-4645-8ad0-326c43517c1a)

We can see Phase shift of 180 degree between input and output.

## Inference

Biasing and MOSFET Operation: Proper biasing is absolutely essential to ensure that the MOSFET works in saturation territory acting as an amplifier.The DC operating point or the Q-point decides the way in which the amplifier will perform, and for this, it has to be set properly so as to produce the required amplification effect.

Effect of Width (𝑊) and Length (L) on  ID​:With an increase in width (W), increase in drain current ID​, hence an induction of higher amplification.The channel length (L) maintains a steady value 180nm meaning that adjustment of W must be performed to achieve the required ID​.

Dependency of Power and Current:Power (=50μW) requirement sets out what drain current must yield (𝐼𝐷=27.78𝜇𝐴I D​ =27.78μA) which again has been proven through simulation via SPICE.The value for W was established via a trial-and-error method experimentally on LTspice.

Observation of AC Analysis:Gain (𝐴V ) and frequency response of an amplifier are all dependent on parameters of MOSFET and external resistances.

Transient Response and Time-Domain Behavior:The amplifier does carry out amplifying of the input signal, as was observed in transient analysis.Any output signal distortions would represent improper biasing or non-linearity on the part of the MOSFET actually doing its work.

# Circuit 2 
 ![Screenshot 2025-02-18 155808](https://github.com/user-attachments/assets/f0be981b-53a4-4c15-a467-8da227e86723)




## Working 

A CMOS inverter (Common Source with Active Load) is depicted in this circuit. Together, NMOS (M1) and PMOS (M2) transistors enhance the input signal. The active load (pull-up network) is the PMOS transistor, and the pull-down network is the NMOS transistor. The output is pulled low by the NMOS when the input voltage is high and high by the PMOS when the input voltage is low. Because of its excellent efficiency and gain, this arrangement is frequently  amplifier circuits.
## Different types of analysis
## DC Analysis
DC analysis means to find the operational point (bias point) MOSFET by calculating some different DC voltages and currents at various nodes of the circuit. For a common source amplifier, we should find the drain current (ID), gate-source voltage (VGS), and check whether the MOSFET is working in cut-off, triode, or saturation regions. It is important to perform the DC analysis since this sets the amplifier for the correct operational bias state before applying an AC signal. In LTspice, the DC analysis is performed using the .op command.
![Screenshot 2025-02-18 153133](https://github.com/user-attachments/assets/ce2b14bb-74ce-4dde-9387-c5e48b159f7d)

## AC analysis 
AC analysis depicts how the amplifier's gain (𝐴𝑣A v​ ) changes with frequency as it is a critical way of studying the frequency response of the amplifier. It also identifies the bandwidth, the -3dB cutoff frequency, and how the amplifier behaves at different frequencies. AC analysis also assumes that there will be small-signal operation; thus, the MOSFET behavior will have to be linearized around its bias point. AC analysis is done in LTspice using the .ac dec 20 0.1 1T command, which sweeps the frequency from 0.1 Hz to 1 THz.
Ac gain can be calulated using equation Av = -gm *Rd
![image](https://github.com/user-attachments/assets/0c3b9e92-de45-427c-926b-557c2637ade9)



## Transient analysis
Transient analysis has been performed to track how the output voltage waveform changes over time with the applied AC input signal. This analysis is further employed to see how amplifiers affect the real-time behavior, including signal amplification and the distortions involved. This helps visualize how the circuit responds to different waveforms such as sine waves or pulses. In LTspice, the transient analysis is done by means of the .tran 5 m command to run the simulation for 5 milliseconds and observe a real-time description of the circuit's activity.
![Uploading image.png…]()



## DC sweep


![Screenshot 2025-02-18 154231](https://github.com/user-attachments/assets/024136f6-05e4-4413-a93a-3b398e5e8525)



## Inference: 

1.DC Analysis- Determines the quiescent operating point and ensures the NMOS operates in the saturation region for proper amplification.  


2.AC Analysis- Examines the small-signal gain of the amplifier. The PMOS active load increases output impedance, leading to improved voltage gain.  


3.Transient Analysis-Validates the amplifier’s response to a time-varying signal. Confirms signal amplification and phase inversion, which is a characteristic of a common source amplifier.  


4.Frequency Response -Identifies bandwidth limitations and cut-off frequencies. Ensures the amplifier functions correctly across the required frequency range.  




   
 




 
 
​ 


