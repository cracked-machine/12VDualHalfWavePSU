# Full-Wave Voltage Multiplier power supplies

<img src="AdjustablePSU/doc/RevC/AdjustablePSU_REVC_POP_3D.png" align="left" height="125" width="250" >


This page contains a design for a bipolar (split +/- voltage rail) linear power supply. It uses variable linear regulators to set the output voltage (via 4 of the resistors).

This design omits the transformer usually found in traditional linear PSU designs. This removes the danger of exposing yourself to lives 240VAC mains. Instead it runs from an AC-AC wall adaptor. *It will not work with an AD-DC wall adaptor!*

A heatsink is also required. The size can vary depending on the current required.

Since the PSU has only two IDC outputs, there is also an extension board available.

<BR>
Both are suitable for use with modular synths systems or as standalone fixed power supplies.



- [Bipolar Linear PSU](Var2IDCAssemblyInstructions.md)

- [Extension board IDCx10](Ext10IDC.md)
