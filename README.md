

(DEU) Das folgende Design zeigt das Standardmodul, das in jeden gewöhnlichen SG3525-Wechselrichter über die Ausgangspins des ICs integriert werden kann, um einen hocheffizienten SG3525-Vollbrücken- oder H-Brücken-Wechselrichter zu realisieren. Mit Bezug auf das obige Diagramm habe ich die vier MOSFETs identifiziert, die als H-Brücke oder Vollbrücken-Netzwerk verschaltet sind. Ich weiß, dass in jeder H-Brücke die MOSFETs diagonal geschaltet sind, um die beabsichtigte Gegentaktleitung über den Transformator oder die angeschlossene Last zu implementieren. Dies impliziert, dass Pin#11 des ICs in diesem Moment auf High ist, was den linken BC547-Schalter eingeschaltet hält.  In dieser Situation geschehen die folgenden Dinge innerhalb der linken BC547-Stufe:
1) Der 100uF-Kondensator lädt sich über die 1N4007-Diode und den mit seinem negativen Anschluss verbundenen Low-Side-MOSFET auf.
2) Diese Ladung wird vorübergehend im Kondensator gespeichert und kann als gleich der Versorgungsspannung angenommen werden.
3) Sobald die Logik des SG3525 im nächsten Oszillationszyklus umschaltet, geht Pin#11 auf Low, was den zugehörigen BC547 sofort ausschaltet.
4) Mit ausgeschaltetem BC547 erreicht die Versorgungsspannung an der Kathode der 1N4007 nun das Gate des angeschlossenen MOSFETs, jedoch wird diese Spannung jetzt durch die im Kondensator gespeicherte Spannung verstärkt, die ebenfalls nahezu der Versorgungsspannung entspricht.
5) Dies führt zu einem Dopplungseffekt und ermöglicht eine erhöhte 2X-Spannung am Gate des entsprechenden MOSFETs.
6) Diese Bedingung schaltet den MOSFET sofort hart ein, was die Spannung über den entsprechenden gegenüberliegenden Low-Side-MOSFET drückt.
7) In dieser Situation wird der Kondensator gezwungen, sich schnell zu entladen, und der MOSFET kann nur so lange leiten, wie die gespeicherte Ladung dieses Kondensators ausreicht.
8) Der Wert des Kondensators wird so gewählt, dass der Kondensator die Ladung für jede Ein/Aus-Periode der Gegentakt-Oszillationen ausreichend halten kann.

