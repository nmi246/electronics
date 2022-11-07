## MOSFETs:
![image](https://user-images.githubusercontent.com/42329930/199118659-e2eadff4-2d91-4639-b045-aeadb145b9dc.png)

## IGBT (Insulated Gate Bipolar Transistor):
![image](https://user-images.githubusercontent.com/42329930/200202296-a24dc8b2-0467-4ec7-9ed5-1f9695ef0642.png)
- The IGBT is a power switching transistor which combines the advantages of MOSFETs and BJTs for use in power supply and motor control circuits.
- is something of a cross between a conventional BJT and a MOSFET, making it ideal as a semiconductor switching device.
- The IGBT combines the insulated gate (hence the first part of its name) technology of the MOSFET with the output performance characteristics of a conventional bipolar transistor, (hence the second part of its name).
- The IGBT has a much lower **on-state** resistance, Ron than an equivalent MOSFET.
- IGBT, MOSFET, BJT comparison table:

| Device Characteristic	| Power  BJT	| Power MOSFET	 | IGBT |
|--|--|--|--| 
| Voltage Rating	| High <1kV	 | High <1kV	| Very High >1kV | 
| Current Rating	| High <500A | Low <200A	| High >500A     |
| Input Drive     |	Current, hFE 20-200mA   | Voltage, VGS 3-10V | Voltage, VGE 4-8V |
| Input Impedance |	Low	      | High	      | High   |
| Output Impedance| Low	      | Medium	    | Low    |
| Switching Speed |	Slow (uS)	| Fast (nS)	  | Medium |
| Cost            |	Low	      | Medium	    | High   |


## Thyristor (aka Silicon Controlled Rectifier, SCR)
| Thyristor 2 transistor analogy | Symbol | Typical thyristor |
|--|--|--|
|![image](https://user-images.githubusercontent.com/42329930/200206097-d1f7d86c-4081-40cd-9a6f-11ed3a01dba3.png) | ![image](https://user-images.githubusercontent.com/42329930/200206129-735d2fcd-8798-44ff-920d-2e5c610e6f41.png) | ![image](https://user-images.githubusercontent.com/42329930/200206152-2edfaee7-6e14-4451-8cd9-67a4f9bcdcea.png) |


| I-V Curve | Phase control |
|--|--|
|![image](https://user-images.githubusercontent.com/42329930/200206049-aae7fc1d-058d-450a-9ab7-b2b897407274.png) |![image](https://user-images.githubusercontent.com/42329930/200206068-0a1c38ef-17a4-439b-ad44-ea9b39c8f866.png)|


- Requires a gate signal to turn **ON**. Once ON it behaves like a rectifying diode. 
- Is unidirectional; only conducts current in one direction. 
- Unlike a diode, it can be made to operate as either an open-circuit switch or as a rectifying diode depending on how the gate is triggered.
- When **ON** and passing current in the forward direction, the gate signal loses control due to the regenerative latching action of the two internal transistors.
- For a thyristor to conduct, its anode current (same as it's load current, IL) must be greater than its holding current value. That is IL > IH.


## Triac
- ![image](https://user-images.githubusercontent.com/42329930/200212150-d44af879-fdcb-4701-b87e-7d264c811f98.png)


## Diodes
- Si, TVS, 


## Optoelectronics
- Optocouplers / isolators
- IR receivers
- optical sensor
- IR emitter
- photo detector
- solid state relays
- IRDC transceiver

## Other 
- chip antenna
- crystals
- fuses
- oscillators

## Resistors
- Thermistors
- trimmers
- varistors
- potentiometers
