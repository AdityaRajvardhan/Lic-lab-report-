## Aim
Design and analyse the MOS differential amplifier circuit by performing DC analysis, Transient analysis, Frequency response for the following specifications 

Vdd=1.8v , P<=2.2mW , Vicm=0.95v , Vocm=1.1v,Vp=0.4v

## Components Required
N channel MOSFET(nmos4),Resistors-1.145kohm(2) ,327.8kohm, Power supply , Connecting wires.

## Theory 

A differential amplifier is an electronic circuit that amplifies the difference between two input voltages while rejecting any common signals. It is a fundamental part of many analog circuits, particularly operational amplifiers and instrumentation amplifiers.

A differential amplifier amplifies the difference between two input signals (V₁ and V₂) while rejecting common signals (noise).

If V₁ > V₂, the output is positive.
If V₂ > V₁, the output is negative.
If V₁ = V₂, the output is zero (ideal case).
The circuit consists of two transistors (BJTs/MOSFETs) with a shared current source. The difference in input voltages changes the current flow, leading to an amplified output.

### Why do we need differential amplifier while we can use normal amplifier circuits ?

High noise rejection (removes common-mode interference).

Better stability and low distortion compared to single-ended amplifiers.
## Cicuit diagram 
![image](https://github.com/user-attachments/assets/0eafbbe4-9966-4a66-9a93-23290c5ace21)


## Procedure 

Step 1: Open LTspice and create a new schematic.

Step 2: Place the following components:

MOSFETs (CMOSN, 180nm technology)
Resistors (R1, R2, R3)
Voltage sources (VDD, differential AC inputs)
Ground connection
Step 3: Set component values and import the MOSFET model.

Step 4: Configure simulation commands:
DC Analysis (.op)
AC Analysis (.ac dec 20 0.1 1T)
Transient Analysis (.tran 5m)

Step 5: Run the simulation and observe results.
Calculate for operating point (Qpoint),Gain,Input and output swing,DC sweep
 
Step 6: Analyze DC biasing, gain vs frequency, and transient response.

## Calculations 
 
![WhatsApp Image 2025-02-28 at 20 29 36_9bf578f2](https://github.com/user-attachments/assets/a118b6b6-4276-4794-a310-f4d88b9442cd)

##  Resukts 
### DC Analysis
### AC Analysis
### Transient Analysis 




