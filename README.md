# Pedal-Isolated-Power-Supply

This is a project folder for a 9 channel isolated power supply. The design is based around the WPDL transformer that steps down 120VAC to 9VAC with 9 separate secondary windings. The isolated secondary windings ensure there are no ground loops contributing to common mode noise. I have a feeling that most cheap power supplies that advertise isolation are not actually truly isolated, I wasn't able to find any other transformers with multiple secondary isloated windings besides the WPDL which is decently bulky. The AC waveform is rectified and and then filtered and passed to linear regulator which holds the DC output at 9V. Each DC output is capable of outputting a continuous 200-300mA. One channel has a current limited LED which features as a power indication light. A 180V MOV on the primary side of the transformer as well as a 19V TVS diode serve as surge protection, while a fast blow 10A fuse on the primary serves as short circuit current protection.

## Features: 

- 9 channel 9VDC 200mA true isolated power 
- Full bridge rectification and filtering 
- MOV and TVS surge protection
- EMI filtering
- Fast blow 10A primary fuse and PTC 300mA secondary fuse
- Power switch and LED for power indication

## Build 


## Functional Circuit Diagram 
![alternative text](https://github.com/ericmaclean/Pedal-Isolated-Power-Supply/blob/main/ScreenShots/FunctionalBlockDiagram%20.png)

## Falstad Current Flow 
![alternative text](https://github.com/ericmaclean/Pedal-Isolated-Power-Supply/blob/main/ScreenShots/Falstad60hztoDCfullbridgerectifier-ezgif.com-video-to-gif-converter.gif)
![alternative text](https://github.com/ericmaclean/Pedal-Isolated-Power-Supply/blob/main/ScreenShots/Falstad_scope_measurements-ezgif.com-video-to-gif-converter.gif)

Visualizing the current we are able to see the current source spiking to charge the capacitor every cycle. This reveals a poor power factor inherent to linear power supplies, poor power factor results in a larger than necessary current flowing through components that aren't contributing to the load power. Current contributes to I^2R heating losses and lead to wear on the transformer, diodes, and capacitors in this circuit. Current spikes can generate odd harmonics that propagate down power lines and cause EMI on neighboring circuits. This can be mitigated with EMI filtering on the power source and adding an inductive choke which resist sharp changes in current, however smoothing the current spikes will result in lower voltage peaks seen by the capacitor reducing the effective DC voltage on the output. Raising the capacitance will reduce the amount of ripple seen by the load, however a larger capacitance will increase the peak supply currents needed to charge the capacitor further contributing the negative factors mentioned above. 

- You can simulate and modify this circuit in Falstad by going here https://www.falstad.com/
- And opening this text file https://github.com/ericmaclean/Pedal-Isolated-Power-Supply/blob/main/falstad/Falstad_LinearRectifier.txt
## LTspice Simulation
![alt text](https://github.com/ericmaclean/Pedal-Isolated-Power-Supply/blob/main/ScreenShots/SpiceSC.png)
## EasyEDA layout and Gerber Files
![alternative text](https://github.com/ericmaclean/Pedal-Isolated-Power-Supply/blob/main/ScreenShots/EasyEDA_Layout.png)

I ordered 10 boards each of which act as a separate channel, ordering the boards individually made the order cheaper and simpler than having one board for everything. On a second revision I would consider making the through holes on the TVS diode larger, the 1.5KE20A TVS diode is rated for a 54A peak current and has mcuh larger leads than I anticiapted.
## Bill of Materials 
I bought all the electronics on mouser but found the enclosures and jacks are much cheaper on Ali Express
- Go here for a complete bill of materials in an excel file https://github.com/ericmaclean/Pedal-Isolated-Power-Supply/blob/main/Power%20supply.xlsx

