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
# Reference circuit schematic.
![CMP](https://user-images.githubusercontent.com/87864756/156195378-af4a9e39-d54d-4e12-a83c-11a10c66b6e8.png)
# Reference waveform schematic.
![ScannerGo_18-2-2022-20 18 34 802-1](https://user-images.githubusercontent.com/87864756/156195920-9962d458-8ee1-41f8-8b98-a77836a34210.png)
# Comparator Schematic in Synopsys custom compiler.

![cmps](https://user-images.githubusercontent.com/87864756/156197377-2f1826b6-0943-4587-ac5d-ebf3bbfa1168.png)
# Symbolic representation of comparator.
![sym](https://user-images.githubusercontent.com/87864756/156197574-88c73640-b594-4db8-8a7f-a7c9386e9f29.png)
# Test Bench for simulation of comparator.
![tb](https://user-images.githubusercontent.com/87864756/156197774-be6e1497-1597-4f4e-b7f4-0b94c425f1c4.png)
# Sine wave response of comparator.
As clearly seen from the simulation results as the magnitude of sine wave increases beyond the reference voltage the outputs are differentiated to positivw and negative saturation voltages.
![sine](https://user-images.githubusercontent.com/87864756/156197986-8c0e5728-a4ab-4764-ad8f-2d2d55963147.png)
# Square wave response of comparator.
![sqr](https://user-images.githubusercontent.com/87864756/156198156-06a8f421-d884-4046-9389-b831bb168094.png)
# Waveform indicating delay in comparator.
The primary factor that affects the propagation delay of a comparator is the output capacitance and stray capacitance. The resistive load at the output also affects the switching speed of a comparator. Optimizing these parameters allows a to select the best tradeoff between propagation delay and noise immunity.
![delay](https://user-images.githubusercontent.com/87864756/156200504-f7421ee6-def2-482a-9b2a-468b22cf1b54.png)
# Stimulus:
Vin+
![Vin+](https://user-images.githubusercontent.com/87864756/156216399-923a5e08-b38f-4b09-9b7e-42b116aeb5a6.png)
Vin-![Vin-](https://user-images.githubusercontent.com/87864756/156216507-fedcf521-2f18-466a-af74-54b398dfe6af.png)
clkA![clkA](https://user-images.githubusercontent.com/87864756/156216546-39cfd182-0bdb-4f35-94b9-62335b8f8c28.png)
clkB![clkB](https://user-images.githubusercontent.com/87864756/156216562-36c1c9ed-ebb4-4a2a-8799-fc73358355fd.png)




# Netlist
*  Generated for: PrimeSim
*  Design library name: test
*  Design cell name: cmp1_TB
*  Design view name: schematic
.lib 'saed32nm.lib' TT

*Custom Compiler Version S-2021.09
*Tue Mar  1 11:37:25 2022

.global gnd!
********************************************************************************
* Library          : test
* Cell             : cmp1
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
.subckt cmp1 vdd vin+ vin- vout+ vout- clka clkb gnd_1
xm33 net5 clkb vdd vdd p105 w=0.8u l=0.03u nf=1 m=1
xm9 net98 clka vdd vdd p105 w=0.6u l=0.03u nf=1 m=1
xm8 net97 clka vdd vdd p105 w=0.6u l=0.03u nf=1 m=1
xm1 vout- vout+ net5 net5 p105 w=0.8u l=0.03u nf=1 m=1
xm0 vout+ vout- net5 net5 p105 w=0.8u l=0.03u nf=1 m=1
xm32 net102 clka gnd_1 gnd_1 n105 w=0.6u l=0.03u nf=1 m=1
xm7 net98 vin- net102 net102 n105 w=0.6u l=0.03u nf=1 m=1
xm6 net97 vin+ net102 net102 n105 w=0.6u l=0.03u nf=1 m=1
xm5 vout+ net98 gnd_1 gnd_1 n105 w=0.8u l=0.03u nf=1 m=1
xm4 vout- net97 gnd_1 gnd_1 n105 w=0.8u l=0.03u nf=1 m=1
xm3 vout- vout+ gnd_1 gnd_1 n105 w=0.3u l=0.03u nf=1 m=1
xm2 vout+ vout- gnd_1 gnd_1 n105 w=0.3u l=0.03u nf=1 m=1
.ends cmp1

********************************************************************************
* Library          : test
* Cell             : cmp1_TB
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
xi0 net17 net11 net9 vout+ vout- net13 net15 gnd! cmp1
v1 net9 gnd! dc=0 sin ( 1 20m 100 0 0 0 )
v5 net17 gnd! dc=1.5
v2 net11 gnd! dc=1
v4 net15 gnd! dc=0 pulse ( 0 1.5 0 0.1n 0.1n 0.5u 1u )
v3 net13 gnd! dc=0 pulse ( 1.5 0 0 0.1n 0.1n 0.5u 1u )








.tran '0.001*(100m-0)' '100m' name=tran

.option primesim_remove_probe_prefix = 0
.probe v(*) i(*) level=1
.probe tran v(vout+) v(vout-) v(net11) v(net13) v(net15) v(net9)

.temp 25



.option primesim_output=wdf


.option parhier = LOCAL






.end
# Conclusion
In this repo we have simulated a daynamic comparator with 28nm CMOS technology with synopsys custom compiler. Simulation results indicate that comparator has successfully discriminated the input voltage levels and provided approximately rail to rail output. This one bit comparator finds potential applications in high-performance ADCs. Also this work can be further extended towards multi bit comparators.

# Author
Suyash Shrivastava, INDIAN INSTITUTE OF SCIENCE EDUCATION AND RESEARCH, BHOPAL
# Acknowledgements
1. https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/
2. https://www.synopsys.com/
3. https://www.vlsisystemdesign.com/
4. Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd.
5. Chinmay Panda, IIT Hyderabad
6. IIT Hyderabad
# References:
1.  D.  Shinkel,  E.  Mensink,  E.  Klumperink,  E.  van  Tuijl,  and  B.  Nauta,“A double-tail latch-type voltage sense amplifier with 18ps Setup+Holdtime,” in Proc. IEEE Int. Solid-State Circuits Conf., Dig. Tech. Papers,Feb. 2007, pp. 314–315[2]  
2. S.  Babayan-Mashhadi  and  R.  Lotfi,  ”Analysis  and  Design  of  a  Low-Voltage Low-Power Double-Tail Comparator,” in IEEE Transactions onVery  Large  Scale  Integration  (VLSI)  Systems,  vol.  22,  no.  2,  pp.  343-352, Feb. 2014, doi: 10.1109/TVLSI.2013.2241799.






