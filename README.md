# Pedal-Isolated-Power-Supply

This a project folder for a 9 channel isolated power supply. The design is based around the WPDL transformer that steps down 120VAC to 9VAC with 9 separate secondary windings. The isolated secondary windings ensure there are no ground loops contributing to common mode noise. I have a feeling that most cheap power supplies that advertise isolation are not actually truly isolated. The AC waveform is rectified and and then filtered and passed to linear regulator which holds the DC output at 9V. 

## Features: 

- 9 channel 9VDC 300mA true isolated power 
- Full bridge rectification and filtering 
- MOV and TVS surge protection
- EMI filtering
- Fast blow 10A primary fuse and PTC 300mA secondary fuse

## Build 


## Functional Circuit Diagram 
![alternative text](https://github.com/ericmaclean/Pedal-Isolated-Power-Supply/blob/main/ScreenShots/FunctionalBlockDiagram%20.png)

## Falstad Current Flow 
![alternative text](https://github.com/ericmaclean/Pedal-Isolated-Power-Supply/blob/main/ScreenShots/Falstad60hztoDCfullbridgerectifier-ezgif.com-video-to-gif-converter.gif)
![alternative text](https://github.com/ericmaclean/Pedal-Isolated-Power-Supply/blob/main/ScreenShots/Falstad_scope_measurements-ezgif.com-video-to-gif-converter.gif)

Visualizing the current we are able to see the current source spiking to charge the capacitor every cycle. This reveals a poor power factor inherent to linear power supplies, poor power factor results in a larger than necessary current flowing through components that aren't contributing to the load power. Current contributes to I^2R heating losses and lead to wear on the transformer, diodes, and capacitors in this circuit. Current spikes can generate odd harmonics that propagate down power lines and cause EMI on neighboring circuits. This can be mitigated with EMI filtering on the power source and adding an inductive choke which resist sharp changes in current, however smoothing the current spikes will result in lower voltage peaks seen by the capacitor reducing the effective DC voltage on the output. 

- You can simulate and modify this circuit in Falstad by going here https://www.falstad.com/
- And opening this text file https://github.com/ericmaclean/Pedal-Isolated-Power-Supply/blob/main/falstad/Falstad_LinearRectifier.txt
## LTspice Simulation
![alt text](https://github.com/ericmaclean/Pedal-Isolated-Power-Supply/blob/main/ScreenShots/SpiceSC.png)
## EasyEDA layout and Gerber Files
![alternative text](https://github.com/ericmaclean/Pedal-Isolated-Power-Supply/blob/main/ScreenShots/EasyEDA_Layout.png)
## Bill of Materials 

Item number	Part	Part description	Unit cost	Quantity	Total cost	Procurement details
1	WPDLXFMR-2	120V - 11V transformer	29.92	1	29.92	WPDLXFMR-2 Transformer – Weber Speakers

2	1N4001G-T	Diodes (35Vrms, 1.1V drop)	0.17	32	5.44	https://www.digikey.com/en/products/detail/diodes-incorporated/1N4001G-T/45749

3	LM2940CT LDO	9V LDO (.8V dropout, 1A)	1.94	7	13.58	https://www.digikey.com/en/products/detail/texas-instruments/LM2940CT-9-0-NOPB/363884

4	MOV-14D181K	180V varistor voltage mov	0.26	3	0.78	MOV-14D181K Bourns Inc. | Circuit Protection | DigiKey

5	10GEEG3E	EMI filter	5.58	1	5.58	10GEEG3E Delta Electronics | Connectors, Interconnects | DigiKey

6	1.5KE20A	TVS diode 17.1V - 27.7V clamp	0.83	7	5.81	1.5KE20A Littelfuse Inc. | Circuit Protection | DigiKey

7	MF-R030	PTC 200mA hold, 600mA trip 60V	0.42	7	2.94	MF-R030 Bourns Inc. | Circuit Protection | DigiKey

8	0217010.HXP	Fuse 10A 250V	0.51	3	1.53	0217010.HXP Littelfuse Inc. | Circuit Protection | DigiKey

9	ali part number	DC female jack type 2 10pc	1.17	1	1.17	10Pcs DC Power Connector pin Female Plug Jack + Male Plug Jack Panel Mount Connector 5.5mm 2.1mm Plug Adapter 2 Terminal Types - AliExpress 13

10	ali part number	DC male jack 10pc	1.52	1	1.52	https://www.aliexpress.us/item/2255800004148598.html?src=bing&aff_short_key=UneMJZVf&aff_platform=true&isdl=y&albch=shopping&acnt=135095331&isdl=y&albcp=555220768&albag=1309519513086509&slnk=&trgt=pla-2333644710812054&plac=&crea=81845026508678&netw=o&device=c&mtctp=e&utm_source=Bing&utm_medium=shopping&utm_campaign=PA_Bing_US_Pmax_ALL_TROAS_20241217_newstore&utm_content=US-ALL&utm_term=DC%20female%20to%20male%20plug&msclkid=7be749d3fb091aa4d2712170744b6a6f&gatewayAdapt=glo2usa

11	ali part number	M2 140pc standoffs	0.99	1	0.99	M2 M2.5 M3 M4 Brass Motherboard Standoffs Hex Board Rack Stud Spacing Screw Hexagon Single Head PCB Pillar Bolts Screw Nut Kits - AliExpress 13

12	ali part number	200x120x75 box	1.7	1	1.7	Outdoor Waterproof Case Enclosure Plastic Box Electronic Project Case Waterproof Junction Box for Electronics - AliExpress

13	ali part number	drill bits	3.87	1	3.87	TOOLEYE HSS Titanium Step Drill Bit Stage Drills For Metal Wood High Speed Stepped Drill Set Power Tools 3-12 4-12 4-20 4-32mm - AliExpress

14	amazon	impact drill	29.99	1	29.99	Amazon.com: FADAKWALT Cordless Drill Set, 20V Electric Power Drill with Battery And Charger, Torque 30N, 21+1 Torque Setting, 3/8-Inch Keyless Chuck, Drill Driver Bits Kit, with LED Electric Drill Set. （green) : Tools & Home Improvement

					104.82	



