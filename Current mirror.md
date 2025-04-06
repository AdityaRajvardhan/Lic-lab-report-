# EXPERIMENT- CURRENT MIRROR 
## AIM 
Design and Analyze Current mirror circuit as active load in amplifier circuit.
Given : Vdd=1.8V, P<=1 mW, Av>-10 V/V.
## COMPONENTS REQUIRED
MOSFETS-nmos pmos , conneccting wire, current source, power supply
## THEORY 

A current mirror is a circuit that copies (mirrors) the current from one branch to another. It uses two matched transistors  MOSFETs to ensure the same current flows in both branches.

![image](https://github.com/user-attachments/assets/e6718cd9-b7e7-4411-8b47-5a4a83d1fc58)

a)Depends on gate-source voltage Vgs matching 

b)M1 is diode connected forcing Vgs1=Vgs2

c)If both MOSFETs have same size and threshold voltage,Iout=Iref.

![image](https://github.com/user-attachments/assets/aff7c721-77fa-4785-bf51-83e12c8083af)
 
### Applications 

Biasing circuits -providing stable currents in amplifiers.

Active loads -replacing resistors in ICs for better performance.

Current sources -delivering fixed current to other parts of a circuit.

## DESIGN CIRCUIT

![1fig](https://github.com/user-attachments/assets/e2e2e156-19a1-4ce3-92c8-fb87951aa6f6)


-  The MOSFET should be in saturation region 
<table>
<td>V1>V<sub>th</sub></td>
</table>
i.e 0.5>0.366
 
  -  I<sub>taotal</sub>=P/V<sub>dd</sub>
<table>
<td>I<sub>total</sub>=0.55mA</td>
</table>
I<sub>total</sub>=I<sub>ref</sub> + I<sub>p</sub>
I<sub>ref</sub>=I<sub>p</sub>=(I<sub>total</sub>)/2
<table>
<td>I<sub>ref</sub>=I<sub>p</sub>=0.27mA</td>
</table>

## DC ANALYSIS 

M1- L=180nm,W=3um

M2- L=180nm,W=3um

M3- L=180nm,W=3.6um

![1a)](https://github.com/user-attachments/assets/faf65dc5-5439-428d-9e03-af46d0b07767)

M1- L=500nm ,W=8.33um

M2- L=500nm ,W=8.33um

M3- L=500nm ,W=9.2um

![1b)](https://github.com/user-attachments/assets/b90aba1c-cdc1-48df-8825-04a7b28652b3)


M1- L=1um ,W=16.65um

M2- L=1um ,W=16.65um

M3- L=1um ,W=20um

![1c)](https://github.com/user-attachments/assets/d13c3db6-c4b0-40f0-a126-f9a6829f12fb)

# Special Case: W/L Ratio of M1:M2 = 1:2

![image](https://github.com/user-attachments/assets/a901904e-5078-425d-8d1d-691adea231b3)

M1:M2=1:2

L=2.38:4.76um ,W=180nm

W/L ratio of M1 and M2 transistors are maintained same i,e 1:2 .


## TRANSIENT ANALYSIS  

![1a](https://github.com/user-attachments/assets/94cb1f83-5359-46b2-809a-73b0d7090169)

Gain = Vout/Vin
     = 280/20.4
     = 13.72

Gain in dB= 20 log(13.72)
          = 22.74

## AC ANALYSIS 

![ac1point061Ghz](https://github.com/user-attachments/assets/63148229-75aa-4324-9b21-97e03f6a50b8)

Frequency = 1.061MHz

Gain in db = 21.008 

## CIRCUIT 2 

![image](https://github.com/user-attachments/assets/d409faa5-8726-445e-92c8-8f806c60225d)


## DC ANALYSIS

 ![image](https://github.com/user-attachments/assets/9c676fc9-7129-4922-8be0-ef8ca60c8efc)

 We can observe that current accross M6 and M3 transistors are almost double because of 1:2 W/L ratio and that of current accross M5 and M4 transistors are same because of 1:1 W/L ratio.


## TRANSIENT ANALYSIS

![image](https://github.com/user-attachments/assets/d9e93798-cde9-4259-b274-6f6272fa0c7f)

Gain= Vout/Vin
    = 1.53/0.099
    = 15.5

Gain in db= 20log(15.5)
          =23.8

## AC ANALYSIS 

![image](https://github.com/user-attachments/assets/3a710b61-386f-4296-8aea-a6438bbc1d2e)

BW= 1.94GHz 

## INFERENCE 

- **Length Increase**: When the length of the NMOSFET is increased, keeping the W/L ratio constant:
  - **V<sub>out</sub>** decreases.
  - **Drain current (I<sub>D</sub>)** increases slightly.
  - **Output resistance** increases due to reduced channel-length modulation.
  - Longer **L** improves **current matching** and **stability** in the current mirror.

- The **differential amplifier** performs better with a **current mirror** instead of a resistor load.
- Using **current mirrors** enhances the **gain and stability** of the amplifier and **reduces offset variations**.

Current Accuracy:The 1:1 ratio offers superior current matching.

The 1:2 ratio results in higher power consumption due to larger devices.

The 1:1 ratio provides better stability due to higher output resistance.
