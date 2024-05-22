The following design shows the standard module which may be integrated to any ordinary SG3525 inverter across the output pins of the IC for accomplishing a highly efficient SG3525 full bridge or H-bridge inverter circuit. Referring to the above diagram, I have identified the four mosfets rigged as an H-bridge or a full bridge network. I know that in any H-bridge the mosfets are configured to conduct diagonally for implementing the intended push pull conduction across the transformer or the connected load. This implies that pin#11 of the IC is high during this instance, which keeps the left side BC547 switch ON. In this situation the following things happen withing the left side BC547 stage:
1) The 100uF capacitor charges up via the 1N4007 diode and the low side mosfet connected with its negative terminal.
2) This charge is temporarily stored inside the capacitor and may be assumed to be equal to the supply voltage.
3) Now as soon as the logic across the SG3525 reverts with the subsequent oscillating cycle, the pin#11 goes low, which instantly switches OFF the associated BC547.
4) With BC547 switched OFF, the supply voltage at the cathode of the 1N007 now reaches the gate of the connected mosfet, however this voltage is now reinforced with the stored voltage inside capacitor which is also almost equal to the supply level.
5) This results in a doubling effect and enables a raised 2X voltage at the gate of the relevant mosfet.
6) This condition instantly hard triggers the mosfet into conduction, which pushes the voltage across the corresponding opposite low side mosfet.
7) During this situation the capacitor is forced to discharge quickly and the mosfet is able to conduct only for so long the stored charge of this capacitor is able to sustain.
The value of the capacitor is selected such that the capacitor is able to adequately hold the charge for each ON/OFF period of the push pull oscillations.

Das folgende Design zeigt das Standardmodul, das in jeden gewöhnlichen SG3525-Wechselrichter über die Ausgangspins des ICs integriert werden kann, um einen hocheffizienten SG3525-Vollbrücken- oder H-Brücken-Wechselrichter zu realisieren. Mit Bezug auf das obige Diagramm habe ich die vier MOSFETs identifiziert, die als H-Brücke oder Vollbrücken-Netzwerk verschaltet sind. Ich weiß, dass in jeder H-Brücke die MOSFETs diagonal geschaltet sind, um die beabsichtigte Gegentaktleitung über den Transformator oder die angeschlossene Last zu implementieren. Dies impliziert, dass Pin#11 des ICs in diesem Moment auf High ist, was den linken BC547-Schalter eingeschaltet hält.  In dieser Situation geschehen die folgenden Dinge innerhalb der linken BC547-Stufe:

