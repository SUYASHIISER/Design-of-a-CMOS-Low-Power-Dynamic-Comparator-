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
![sine](https://user-images.githubusercontent.com/87864756/156197986-8c0e5728-a4ab-4764-ad8f-2d2d55963147.png)
# Square wave response of comparator.
![sqr](https://user-images.githubusercontent.com/87864756/156198156-06a8f421-d884-4046-9389-b831bb168094.png)
# Waveform indicating delay in comparator.
![delay](https://user-images.githubusercontent.com/87864756/156200504-f7421ee6-def2-482a-9b2a-468b22cf1b54.png)
# Author
Suyash Shrivastava, INDIAN INSTITUTE OF SCIENCE EDUCATION AND RESEARCH, BHOPAL
# Acknowledgements
1. https://www.iith.ac.in/events/2022/02/15/Cloud-Based-Analog-IC-Design-Hackathon/
2. https://www.synopsys.com/
3. https://www.vlsisystemdesign.com/
Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd.
Chinmay Panda, IIT Hyderabad
IIT Hyderabad
# References:
[1]  D.  Shinkel,  E.  Mensink,  E.  Klumperink,  E.  van  Tuijl,  and  B.  Nauta,“A double-tail latch-type voltage sense amplifier with 18ps Setup+Holdtime,” in Proc. IEEE Int. Solid-State Circuits Conf., Dig. Tech. Papers,Feb. 2007, pp. 314–315[2]  S.  Babayan-Mashhadi  and  R.  Lotfi,  ”Analysis  and  Design  of  a  Low-Voltage Low-Power Double-Tail Comparator,” in IEEE Transactions onVery  Large  Scale  Integration  (VLSI)  Systems,  vol.  22,  no.  2,  pp.  343-352, Feb. 2014, doi: 10.1109/TVLSI.2013.2241799
S.  Babayan-Mashhadi  and  R.  Lotfi,  ”Analysis  and  Design  of  a  Low-Voltage Low-Power Double-Tail Comparator,” in IEEE Transactions onVery  Large  Scale  Integration  (VLSI)  Systems,  vol.  22,  no.  2,  pp.  343-352, Feb. 2014, doi: 10.1109/TVLSI.2013.2241799.






