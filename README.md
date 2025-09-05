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




