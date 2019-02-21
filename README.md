# Symmetric-switched-mode-power-supply-SMPS-
**This is both a single and symmetric power supply for electronic instrumentation circuits**


**WELCOME ALL!**


I'm finally releasing a power supply that I designed during a project that required three voltages: +/- 15 V @ 500 mA and +5V @ 1A.

They are based on the following chips:

1. [LT1371](https://www.analog.com/media/en/technical-documentation/data-sheets/1371fa.pdf), a 3A 500 kHz switching regulator in flyback mode to obtain the +/-15V output.

2. [LT1173](https://www.analog.com/media/en/technical-documentation/data-sheets/lt1173.pdf), a micropower DC/DC converter fixed to 5V via a step-down mode configuration

This power supply was used with a battery pack (Li-Ion 3S) and therefore incorporates a low battery detection system. In addition, it can be digitally driven and interfaced with a microcontroller. A pin header makes GND, LO-BAT and PS_ON acessible (only the symmetrical voltage, the 5V PS is permanent). 

Each output can be physically disabled via its respective jumper. This feature also helps on routing the power supply through a different connection instead of using the screw terminals.

The nominal voltage for the battery pack should be 11.1 V or 12.6 when fully charged. If the voltage drops below its 35% (approx. 11.3V) then the output of the comparator is triggered. I will provide a mathematical description of the detection voltage. It is based on an TL431 and an LM311 as a voltage comparator with a specific voltage divider. Please give me some time to check my notes an give you the threshold adjustment values. A preset is used for this adjustment.

In case the power supply is used without digital control simply connect the jumper to the right position to enable the power supply.

Here's a view of the PCB (first revision) drawn in Proteus 8.4/8.6.

![alt text](https://github.com/dzalf/Symmetric-switched-mode-power-supply-SMPS-/blob/master/Proteus%20Design/2017-03-10%2016_36_07-Power%20source%20for%20CS%20-%20Proteus%208%20Professional%20-%20PCB%20Layout.png)

**#TODO**

There are several pending improvements, however the power supply works acceptably well. 

1. One of the main issues to tackle is the output ripple which is minimised by a passive subber and RLC filter at the output.
2. The footprint from the LM311 was different fro the actual device and thus the first version has an error that made necessary to use a jumper wire to correct this.
3. Port it to kiCAD!


Cheers! :beer:

dzalf :sunglasses: 
