
## Bipolar Linear PSU

<img src="AdjustablePSU/doc/AdjustablePSU3D.png" height="300" width="600" >


### Some notes regarding safety

Unless you want to make the circuit go bye-bye here are some important notes. *I accept no responsibility for damage to equipment, heightened pulse rate, loss of limbs, etc..*

1) The PSU output current is limited by the wall adaptor used and the components used in the design are limited to using a 3A wall adaptor.

2) If sourcing your own capcaitors, you must ensure that wall adaptor voltage does *not* exceed the absolute max 80% of the voltage rating of the capacitors. See the "Adjusting output voltage" section below.

3) Polarity of these components *must* be observed or things will explode.

### Power source (Wall Adaptor)

This design uses a AC-AC wall adaptor as a power source. This is essentially a step down transformer with (hopefully) a fuse. Here is a well-stocked UK supplier.

[www.poweradaptorsuk.co.uk](https://www.poweradaptorsuk.co.uk/category_s/38.htm) 

You can also try Ebay, etc.
<details>
  <summary>click me</summary>  
  some text
</details>  
  
While we must allow for voltage drop and temp characteristics of the regulator ICs, the wall adaptor is outputing peak-to-peak AC voltage into the PSU circuit. Therefore the actual regulated output voltage of the PSU circuit is Vrms (Vp-p * 1.414), not Vp-p. Therefore, rather than use a 15V wall adaptor (to allow for voltage dropout issues), we can use a 12Vac wall adaptor to power a regulated +/-12Vdc PSU.  

Vp-p | Vrms | Voltage drop | Dissipation @ 1A
|:-:|:----:|:------------:|:----------------
5   |7.07   |2.07         | 3.1W
9   |12.7   |3.7          | 5.55W
12  |16.9   |4.9          | 7.35W
18  |25.4   |7.4          | 11.1W
24  |33.9   |9.9          | 14.85W


### Adjusting output voltage

The output voltage can be set by changing the four resistors marked on the back of the PCB.

R1     | R2     | Output Voltage  | Min. Filter Cap Rating
|:-----------    |:------------:|:---------------:|:----------:|
120R   |390R    | +/- 5V  | 8V
120R   |750R    | +/- 9V  | 16V
120R   |1K1     | +/-12V  | 20V
150R   |2K      | +/-18V  | 32V
120R   |2K2     | +/-24V  | 35V

The above table is printed - and the specific resistors are highlighted - on the reverse of the PCB. 

### Selecting filter capacitor values

The 16mm diameter electrlytic capacitors filter noise and ripple from the main supply. There are four filter capacitors per power rail, eight in total.

The ripple current for each power rail is proportional to the sum of its four capacitors. Therefore, if you have lower current requirements you can select lower capacitor values without sacrificing acceptable filtering. Use the tables below to select the capacitor values. Note, for practical reasons, these have been rounded to common E12/E24 values.

The table below shows *individual* capacitor values for corresponding output ripple:

Total Current|&nbsp;&nbsp;|Ripple|Each Cap|&nbsp;&nbsp;|Ripple|Each Cap|&nbsp;&nbsp;&nbsp;|Ripple|Each Cap|
|:------------|------|:----:|:------:|--:|:----:|:--------------:|:--:|:----:|:--------------:|
50mA         |       |0.5Vpp|120uF|   |0.3Vpp|220uF|   |0.1Vpp|680uF|
100mA        |       |0.5Vpp|220uF|   |0.3Vpp|470uF|   |0.1Vpp|1200uF|
250mA        |       |0.5Vpp|560uF|   |0.3Vpp|1200uF|   |0.1Vpp|3300uF|
500mA        |       |0.5Vpp|1200uF|   |0.3Vpp|2200uF|   |0.1Vpp|6800uF|
1A           |       |0.5Vpp|2700uF|   |0.3Vpp|3900uF|   |0.1Vpp|120mF|
1.5A         |       |0.5Vpp|3900uF|   |0.3Vpp|5600uF|   |0.1Vpp|240mF|

*Capacitors must not exceed their voltage rating! See safety section above.*


### Heatsinks

The regulators *will* need a heatsink or they will shutdown before they can output any siginificant current.

This PSU is designed to be used with Fischer Elektronic heatsinks, but any heatsink below the following will meet disipation requirements up to 1.5 amps.

My preference are these clip-type heatsinks that can be used as a joint heatsink by both regulators:

- [SK 574/37,5 SA](https://uk.rs-online.com/web/p/heatsinks/7226906/) - Shorter but extends beyond PCB footprint
- [SK 575/50 SA](https://uk.rs-online.com/web/p/heatsinks/7226864/)   - Taller but fits within the PCB footprint

It is recommended that you clip the ICs to the heatsink before mounting them on the board.

If you want to source alternative heatsinks, the PCB has max space for ~50mm width.  Screwholes are M3.  
The table below can be used to determine the appropriate thermal resistance of the heatsink.

12v wall adaptor regulating at 12V output only.

PSU input voltage | PSU Output Current |Heatsink Power Dissipation | Joint Heatsink  | Two Heatsinks (one per regulator)
|:----------------|:----------------:|:-------------------------:|:---------------:|:---------------------------:|
12Vp-p               |400mA             | 1.9W                      |92K/W            |46K/W
12Vp-p               |750mA             | 3.7W                      |45K/W            |22K/W
12Vp-p               |1A                | 4.9W                      |30K/W            |15K/W
12Vp-p               |1.5A              | 7.4W                      |20K/W            |10K/W


