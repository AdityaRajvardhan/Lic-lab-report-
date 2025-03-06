## Aim
Design and analyse the MOS differential amplifier circuit by performing DC analysis, Transient analysis, Frequency response for the following specifications 

Vdd=1.8v , P<=2.2mW , Vicm=0.95v , Vocm=1.1v,Vp=0.4v

## Components  Required
N channel MOSFET(nmos4),Resistors-1.145kohm(2) ,327.8kohm, Power supply , Connecting wires.

## Theory 

A differential amplifier is an electronic circuit that amplifies the difference between two input voltages while rejecting any common signals. It is a fundamental part of many analog circuits, particularly operational amplifiers and instrumentation amplifiers.

![image](https://github.com/user-attachments/assets/709e0b03-fb58-4212-ba6c-cd3ee333a56c)

The basic MOS differential-pair configuration.

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

##  Results 
### DC Analysis
To do circit analysis first we need to check that the Both the MOSFET should be in the Saturation Region which should satisfy this;

VDS > VGS - Vth
![image](https://github.com/user-attachments/assets/26731324-ba67-479e-804b-d4ad1d4a568d)
Lenght:200n 

Width:120.48u
                       
   Id1 = Id2 => 0.611mA , Vocm1 = Vocm2 -> 1.1V 

                          Operating point of NMOSFETS = (1.1 V, 0.611mA)

The above length and width helps Mosfet to run in saturation region 

### Transient Analysis 

Transient analysis has been performed to track how the output voltage waveform changes over time with the applied AC input signal. This analysis is further employed to see how amplifiers affect the real-time behavior, including signal amplification and the distortions involved. .tran 5 m command to run the simulation for 5 milliseconds and observe a real-time description of the circuit's activity.


![image](https://github.com/user-attachments/assets/ff118670-c278-4b2a-8fe2-563c625e3039)
We can see Phase shift of 180 degree between input and output.

Green line represents Vout and blue line represends Vicm 
Av = Vout/Vin

   = 1.72-1.027/1-0.99

   = 0.145/0.1

 Av = 1.45

Gain in db=20log(1.45)
       
          =3.227 dB



### AC Analysis
The AC analysis plot shows the frequency response of the circuit, where the gain remains stable in the mid-frequency range before rolling off at higher frequencies. The mid-band region exhibits a nearly constant gain, indicating the circuit's operational bandwidth, while the high-frequency roll-off suggests the presence of dominant poles limiting the bandwidth.

![image](https://github.com/user-attachments/assets/97102a1c-3f03-4bfd-8bc9-2399891c3d64)


Av=1.203 

Gain=20log(Av)

    =20 log(1.203)
   
    =1.605
 
By calculating from graph we can say Therotical nad experiment value of mid band frequency is approximatly equal.

## DC sweep 

![image](https://github.com/user-attachments/assets/c8675df4-9f30-4952-abe9-5da53982b9c1)


The crossover voltage (where Vocm1 = Vocm2) represents the bias point at which both transistors conduct symmetrically.

The linear variation of the output voltages indicates proper biasing of the NMOS transistors.

## Circuit 2

In this circuit we will be replacing Rss with current source and other terminal to ground.
Current source of 1.22
![image](https://github.com/user-attachments/assets/5143f461-5812-40f0-81ab-32c78d605fe2)

## Dc Analysis 
To do circit analysis first we need to check that the Both the MOSFET should be in the Saturation Region which should satisfy this;

VDS > VGS - Vth

![image](https://github.com/user-attachments/assets/beb58d08-9b31-4e22-b5b3-abaa82105a6b)

Lenght:200n 

Width:120.48u

 Id1 = Id2 => 0.611mA , Vocm1 = Vocm2 -> 1.1V 

                          Operating point of NMOSFETS = (1.1 V, 0.611mA)

The above length and width helps Mosfet to run in saturation region 

## Transient Analysis 
Transient analysis has been performed to track how the output voltage waveform changes over time with the applied AC input signal. This analysis is further employed to see how amplifiers affect the real-time behavior, including signal amplification and the distortions involved. .tran 5 m command to run the simulation for 5 milliseconds and observe a real-time description of the circuit's activity.

![image](https://github.com/user-attachments/assets/ac383264-8928-4fc2-929b-a2415b690fc2)

Av = Vout/Vin

   = 1.5369-0.6623/1-0.9
   = 0.8746/0.1
Av = 8.74

Gain in dB=20log(8.74)
          = 18.830 dB

## AC Analysis 

The AC analysis plot shows the frequency response of the circuit, where the gain remains stable in the mid-frequency range before rolling off at higher frequencies. The mid-band region exhibits a nearly constant gain, indicating the circuit's operational bandwidth, while the high-frequency roll-off suggests the presence of dominant poles limiting the bandwidth.
 
![image](https://github.com/user-attachments/assets/9db5e817-b7b6-4cb4-9f1f-76dc034287cd)

If the drain resistors were increased, the output voltage swing would be greater, leading to a steeper slope.
Decrease in resistance would reduce the voltage gain, making the curves less steep.

This happend because Resistance Rss was directly replaced with current source leading to increase in resistance and hence gain is increased. 

Av=2.877

Gain=20log(Av)

    =20 log(2.877)
    
    = 9.178

## DC sweep 

![image](https://github.com/user-attachments/assets/8043d826-8c54-480d-a053-678183360fe8)

Observations from first circuit 's DC sweep to  differential MOS with current source 

There is shift in Crossover Point that is  intersection occurs at a different voltage.

There is change in Slope as The rate of voltage variation is different.

If the drain resistors were increased, the output voltage swing would be greater, leading to a steeper slope.
Decrease in resistance would reduce the voltage gain, making the curves less steep.This happend because Resistance Rss was directly replaced with current source leading to increase in resistance and hence gain  

## Circuit 3 

Differential amplifier circuit, with NMOS M3 acting as current source

![image](https://github.com/user-attachments/assets/8eddb515-224f-456d-89d0-80d3648328a4)

By varying V1 values and keeping Mosfet in saturation region as per calculations we can obtain operating points.
V1 for the M3 is 0.5725 V, which will give us I of 1.222 mA, VD3 of around 0.414 V, which is not exactly the Vp we need but is close.

## Dc analysis 
To do circit analysis first we need to check that the Both the MOSFET should be in the Saturation Region which should satisfy this;

VDS > VGS - Vth

![WhatsApp Image 2025-03-06 at 00 14 35_65062030](https://github.com/user-attachments/assets/73c96e0a-ec9d-4b8e-b3ac-d1e3ce13bbfe)

Lenght:180n 

Width:125u

 Id1 = Id2 => 0.6113mA , Vocm1 = Vocm2 -> 1.10026V 

                          Operating point of NMOSFETS = (1.10026 V, 0.6113mA)
The above length and width helps Mosfet to run in saturation region 


## Transient Analysis

Transient analysis has been performed to track how the output voltage waveform changes over time with the applied AC input signal. This analysis is further employed to see how amplifiers affect the real-time behavior, including signal amplification and the distortions involved. .tran 5 m command to run the simulation for 5 milliseconds and observe a real-time description of the circuit's activity.


![WhatsApp Image 2025-03-06 at 13 18 24_68198a9d](https://github.com/user-attachments/assets/af817e07-82e6-4548-85f2-63e02612d01d)

 Voltage Gain = Vo/Vi 

              =1.53566-0.006606/0.1

              =15.29054 V/V 

 Gain in dB = 20log(15.29) 

            = 23.6 dB


## AC Analysis

The AC analysis plot shows the frequency response of the circuit, where the gain remains stable in the mid-frequency range before rolling off at higher frequencies. The mid-band region exhibits a nearly constant gain, indicating the circuit's operational bandwidth, while the high-frequency roll-off suggests the presence of dominant poles limiting the bandwidth.

![image](https://github.com/user-attachments/assets/e9762988-bc8f-418d-840c-cf5896f7a909)




## Inference 






