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



## TRANSIENT ANALYSIS  

![1a](https://github.com/user-attachments/assets/94cb1f83-5359-46b2-809a-73b0d7090169)

## AC ANALYSIS 

![1a5point175Ghz](https://github.com/user-attachments/assets/a3f5fa0b-ac70-42f1-886e-63c5fcd7bae4)



