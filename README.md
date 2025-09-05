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


## Falstad Circuit Flow 
![alternative text](https://github.com/ericmaclean/Pedal-Isolated-Power-Supply/blob/main/ScreenShots/Falstad60hztoDCfullbridgerectifier-ezgif.com-video-to-gif-converter.gif)
![alternative text](https://github.com/ericmaclean/Pedal-Isolated-Power-Supply/blob/main/ScreenShots/Falstad_scope_measurements-ezgif.com-video-to-gif-converter.gif)
## LTspice Simulation
![alt text](https://github.com/ericmaclean/Pedal-Isolated-Power-Supply/blob/main/ScreenShots/SpiceSC.png)
## EasyEDA layout and Gerber Files
![alternative text](https://github.com/ericmaclean/Pedal-Isolated-Power-Supply/blob/main/ScreenShots/EasyEDA_Schematic.png)
![alternative text](https://github.com/ericmaclean/Pedal-Isolated-Power-Supply/blob/main/ScreenShots/EasyEDA_Layout.png)
## Bill of Materials 




