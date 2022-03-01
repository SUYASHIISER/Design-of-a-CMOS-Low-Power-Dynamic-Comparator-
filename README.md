# Design-of-a-CMOS-Low-Power-Dynamic-Comparator-
 This repository presents the design of low power dynamic comparator with CMOS technology using synopsys custom compiler.
# Introduction
Every A–D converter uses one or more analog comparators. An analog, or magnitude, comparator is a device which has two analog inputs, like an operational amplifier, and one output which is assumed to have only two states, generally compatible with the input of one of the logic circuit families. The output is in the ‘high’ (positive) state when the non-inverting input is more positive than the inverting one. It is in the ‘low’ state when the inverting input is more positive than the non-inverting one. It is assumed that the two inputs are never exactly the same.
# Dynamic comparator
This section introduces the conventional two-stage dynamic comparator. It comprises of a pre-amplifier stage
and a latching stage. The low-tail current of the preamplifier stage is most preferred to minimize the input offset
voltage. The latching stage is generally designed to produce a large operational current to increase the speed of
operation.
When clock input is set to Vdd, transistors M3 and M4 are in OFF condition. At the same time, transistors
M1 and M2 are in ON condition. The nodes Fn and Fp will be discharging. During the comparison phase in this
design, when clock input is set to low, transistors M1 and M2 are in OFF condition. At the same time, M3 and M4 are in ON condition. During this period of time, the paths Fn and Fp are charged to Vdd. Meanwhile this causes the
output paths Outp and Outn to discharge through transistors MR1 and MR2 to the ground.
This two-stage technique has an advantage of resulting in low kick-back noise which is further useful
for low-voltage applications. This conventional dynamic comparator is simulated on 28nm CMOS technology
using synopsys custom compiler.
