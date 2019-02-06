## Variable PSU

### Specifications

- Max Input voltage: 12VAC (16.9VAC RMS) @ 3A (using AC-AC plug pack)
- Max output Voltage: +/- 12VDC @ 2A (1A per rail)
- Load Regulation: 5%
- Ripple: 0.75 Vpp @ 1A

### Assembly Instructions


1. Solder the capacitors, diodes and resistors. Note the polarity of the diodes and caps!

![](./AdjustablePSU/doc/InstructionsImages/AdjustablePSU3D_1.png)

2. Solder the headers and final diodes. Note the polarity of the diodes!

![](./AdjustablePSU/doc/InstructionsImages/AdjustablePSU3D_2.png)

3. Solder the adjustment resistors on the back of the PCB (for esy access)

![](./AdjustablePSU/doc/InstructionsImages/AdjustablePSU3D_3.png)

4. Attach the two ICs to the heatsink using the clips. This should be done *before* soldering the parts to the PCB:

- Line up the IC on the heatsink so that the legs are protruding below the edge of the heatsink.
- Lay the clip on top of the IC so that ridge of the clip is lined up with the notch in the heatsink
- Apply gentle force to the right angle of the clip until it inserts into the notch. A pair of pliers or a *vice* can be useful.

5. Solder the IC legs to the PCB. Attach the heatsink to the PCB using the screwholes, taking care to keep the screws straight as you  turn them.

![](./AdjustablePSU/doc/InstructionsImages/AdjustablePSU3D_4.png)

6. Solder the Electrolytic caps. Note the polarity of the caps!

![](./AdjustablePSU/doc/InstructionsImages/AdjustablePSU3D_5.png)

### Schematic

For reference:

![](./AdjustablePSU/doc/InstructionsImages/AdjustablePSU.svg)


### Typical Characteristics
|     |     |
|:---:|:---:|
|![OutputCurrentVsOnLoadOutputVoltage](./AdjustablePSU/doc/Characteristics/Output%20Current%20vs.%20On-Load%20Output%20Voltage.svg)|![OutputPowerVsOnLoadOutputVoltage](./AdjustablePSU/doc/Characteristics/Output%20Power%20vs.%20On-Load%20Output%20Voltage.svg)|
|![OutputCurrentVsLoadRegulation](./AdjustablePSU/doc/Characteristics/Output%20Current%20vs.%20Load%20Regulation%20(per%20rail).svg)|![OutputPowerVsLoadRegulaton](./AdjustablePSU/doc/Characteristics/Output%20Power%20vs.%20Load%20Regulation%20(per%20rail).svg)|
|![OutputCurrentVsOutputImpedance](./AdjustablePSU/doc/Characteristics/Output%20Current%20vs.%20Output%20Impedance%20(per%20rail).svg)|![OutputPowerVsOutputImpedance](./AdjustablePSU/doc/Characteristics/Output%20Power%20vs.%20Output%20Impedance%20(per%20rail).svg)|
|![OutputCurrentVsRippleVpp](./AdjustablePSU/doc/Characteristics/Output%20Current%20vs.%20Ripple%20(per%20rail).svg)|![OutputPowerVsRippleVpp](./AdjustablePSU/doc/Characteristics/Power%20output%20vs.%20Ripple%20(per%20rail).svg)|
