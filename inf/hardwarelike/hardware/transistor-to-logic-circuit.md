# transistor → logic gate → logic circut

## transistors

A transistor has three terminals.
In a transistor, if you apply power to two certain terminals, power can flow through two other terminals. (of course, between both of the sets of the terminals, one will be the same.

flex-container:✫sm_transistor-current-explanation.png✫

BJT  Bipolar junction transistor
The three terminals in a bipolar transistor are called ⟮base⟯, ⟮collector⟯, and ⟮emitter⟯.
BJT are either PNP or NPN.
NPN transistor  Negative Positive Negative transistor
PNP transistor  Positive Negative Positive transistor
for NPN transistors, applying power (at the base) allows the current to flow.
for PNP transistors, applying negative/no power (at the base) allows the current to flow.
For NPN BJT transistors, if you apply power to the base, it will flow to the emitter, allowing a stronger current to flow between collector and emitter.

flex-container:✫sm_tmpr_uvk0fj.png✫


flex-container:✫sm_tmpadmp5k8t.png✫
The three terminals in a field-effect transistor (FET) transistor are called ⟮gate⟯, ⟮source⟯, and ⟮drain⟯.
FET  Field-effect transistor
MOSFET   metal–oxide–semiconductor field-effect transistor
CMOS|Complementary metal–oxide–semiconductor
MOSFET is the most common type of FET.
most ICs that use MOSFETs are manufactured with CMOS

today, most ICs are made with CMOS-manufactured MOSFETs

## logic gates

Logic gates are made up of a few transistors in a specific arragnement (depending on the gate).

XOR|✫sm_120px-XOR_ANSI_Labelled.svg.png✫
XNOR|✫sm_120px-XNOR_ANSI_Labelled.svg.png✫
OR|✫sm_120px-OR_ANSI_Labelled.svg.png✫
NOT|✫sm_120px-NOT_ANSI_Labelled.svg.png✫
NOR|✫sm_120px-NOR_ANSI_Labelled.svg.png✫
NAND|✫sm_120px-NAND_ANSI_Labelled.svg.png✫
AND|✫sm_120px-AND_ANSI_Labelled.svg.png✫

Either NAND or NOR gates could be used to create any possible logic circuit since they are functionally complete 
Today, NAND is the most commonly used logic gate, since it's functionally complete and can be built with few trasnistors

## circuits

A ⟮logic circuit⟯ consists of interconnected logic gates.
A combinatorial logic circuit is one whose output only¬ depends on its input.
A sequential logic circut is one whose output depends on its input, and the previous state.
