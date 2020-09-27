## +/-12V output, dual half-wave PSU

Gerbers and BOM files can found in the doc folders.

![](FixedPSU/doc/FixedPSU3D.png)

Now some random instructions and ramblings...

This unit provides a +12V and -12V DC output voltage without a centre-tapped transformer by using a dual half-wave rectifier design. The transformer must be provided by means of an external plug pack.

This is a common design that can be found online including - but not limited to - Ray "MFOS" Wilson, FrequencyCentral, numerous textbooks..!

The positive going AC waveform is rectified and smoothed to positive DC on one wire. The negative going AC waveform is rectified and smoothed to negative DC on the other wire.

![](FixedPSU/doc/FixedPSUSchematic.svg)

It's a rather noisy circuit. This is a limitation with the half-wave rectifier design; the changing AC waveform and reverse bias of the rectifier causes the transformer output inductance to collapse abruptly, causing a voltage spike at the transformer output. Perhaps a snubber network across the inputs would help. A full-bridge-rectifier or SMPS design with adequate filtering would be a better but ultimately, more expensive solution.

To prevent excessive noise, it's not recommended that the current draw is taken past ~750mA!

*It will not work with an AD-DC wall adaptor*. You must use a AC-AC wall adaptor (12VAC @ 1500mA or higher is recommended). These are not so common today but can be found on Ebay (search for "AC/AC adaptor").

A heatsink is also required for the voltage regulators. Fischer Elektronik SK 574/50 is suggested: https://uk.rs-online.com/web/p/heatsinks/7226909/

Since the PSU has only two IDC outputs, there is also an extension board available.

This circuit is relatively safe (compared to an offline AC/AC PSU) but common sense should be exercised when it comes to electrical safety. Other than you own personal safety, some pointers on preventing the magic smoke:

- Take care not to mix up the pos/neg regulator ICs. L7912 is the negative regulator and L7812 is the positive regulator!

- If you reverse the polarised caps or diodes they will go pop when you power the unit up. You have be warned! :D
