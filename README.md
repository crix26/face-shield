# Behelfs-Gesichtsmasken SCHNELL drucken
Einige Dateien und Dokumentation darüber wie man die Prusa Gesichtsschilde sehr schnell drucken kann.

## Disclaimer

Diese Dateien werden "wie sie sind" und ohne Garantien oder Gewährleistungen irgendwelcher Art bereitgestellt. 

These design files are provided "AS IS" WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied, including, without limitation, any warranties or conditions of TITLE, NON-INFRINGEMENT, MERCHANTABILITY, or FITNESS FOR A PARTICULAR PURPOSE.

Es handelt sich ausdrücklich nicht um ein Medizinprodukt. Betrachte es als Karnevalsverkleidung! Es ist werder zertifiziert noch geeignet für irgendeine Verwendung.

## TL;DR

* Benutze den `PrusaSlicer`
* Setze alle Geschwindigkeiten (abgesehen von `Stützstrukturen`, `Überbrückungen`, `Lückenfüllung`, und `Geschwindigkeit der ersten Schicht`) auf Deine `Eilgang` Geschwindigkeit. Die wirklich erreichten Geschwindigkeiten werden durch den Slicer automatisch auf die `Maximale Volumengeschwindigkeit` des Filaments begrenzt. Der Drucker wird nicht die oben eingestellten Geschwidigkeiten erreichen, wird aber so schnell wie möglich drucken.
* Setze die `Maximale Volumengeschwindigkeit` des Filaments um darüber die Druckgeschwindigkeit zu steuern. Mit einer 0.4 mm Düse, beginne bei 8 mm³/s, und erhöhe den Wert um das Maximum deiner Druckers zu finden. 17 mm³/s sind für eine E3D V6 Düse mit 0.8mm OK.
* Setze 0% Infill
* Setze 0.87 mm Standardextrusionsbreite wenn Du das `stl/Covid-19 Shield v10.stl` Modell druckst
* Wenn der Extruder Schritte verliert (laute, klackende Geräusche), verringere die `Maximale Volumengeschwindigkeit`. Oder erhöhe die Düsentemperatur, so dass das Filament schneller schmilzt.

## Häufig gestellte Fragen

Q: Das `Prusa Face Shield RC3` braucht sehr lange auf dem Drucker und das Virus verbreitet sich exponentiell! Wie kann der Druck beschleunigt werden?

A: Guter Punkt! Das ist genau das Thema dieses Guides. Ich werde Dich durch alle wichtigen Dinge und Einstellungen leiten die zu beachten sind um die Druckzeit zu verringern.

Q: Ist Deine optimierte Version stark genug? [Josef Prusa sagte auf Twitter](https://twitter.com/josefprusa/status/1242931010641244161), dass wir das Design nicht ändern sollten weil es stark sein muss.

A: Ich weiß es nicht. Josef Prusa hat keine Begründung genannt warum das Teil so designed wurde. Ich denke die optimierte Version ist auch gut. Sie ist nicht so starr wie das Original und etwas flexibler. Wenn Du meinst die verbesserte Version ist nicht stark genug, gibt es andere Optionen. Wenn Du auf der sicheren Seite sein willst, drucke `stl/covid19_headband_rc3_no_text v1.stl`. Das ist die Originalversion ohne den Text, so dass sie etwas schneller druckt.

Schau Dir [hier](quality_control.md) an wie man das Teil misshandeln kann ohne dass es bricht.

Q: Wie viel schneller können wir werden?

A: Hier sind einige von `PrusaSlicer` erwartete Druckzeiten berechnet für einen Prusa i3 MK2.5 mit PETG:

* original Datei mit `0.20mm SPEED` Einstellung (eines der Prusa Standardprofile): 3:17h
* original Datei mit den Settings aus `covid19_headband_rc3_1pcs.3mf` von der Originalwebseite: 2:36h
* `stl/covid19_headband_rc3_no_text v1.stl` mit `0.20mm SPEED` Einstellungen (eines der Prusa Standardprofile): 3:12h
* `stl/Covid-19 Shield v10.stl` mit optimierten Einstellungen: 0:43h
* `stl/Covid-19 Shield v10.stl` mit optimierten Einstellungen und einer 0.8mm Düse: 0:36h
* `stl/Covid-19 Shield v18.stl` mit optimierten Einstellungen und einer 0.8mm Düse: 0:31h

Q: Ich will über Nacht drucken und nicht jede Stunde den Druck wechseln?

A: Du hast Glück, es gibt gestapelte Versionen von 2 bis 9 Teilen übereinander. Sie ist leicht in ca 1h pro Teil mit einer 0.4mm Düse druckbar. Configuration für Slic3r: `layer: 0.25mm, all speeds to 150mm/s, bridging speed to 50mm/s, gap fill to 0mm/s, PLA, enable detect bridging perimeters`.

Q: Ich nutze Cura zum slicen meiner STL's, kannst Du einen Guide dafür anbieten?

A: Zum aktuellen Zeitpbnkt kann ich nur diesen Guide für `PrusaSlicer` anbieten. Wusstest Du dass `PrusaSlicer 2.2` den `Ender 3` von Haus aus unterstützt? Vielleicht möchtest Du es ausprobieren!

Q: Kannst Du eine 888 Version für A4 Folien bereitstellen?

A: Kurze Antwort: Gute Idee, ein Krankenhaus hat uns auch nach breiteren Schilden gefragt, und wir haben einen Prototypen gemacht. Unsere Ergebnisse waren maximal mittelmäßig, also haben wir die Idee verworfen und haben uns auf die `v18` konzentriert. Lange Antwort: 888 punches are not close to the edge, the sheet will not bend properly around the printed part. You could solve this with extra hooks that catch the sheet at the ends. However, this would not work with thick sheets (0.8 mm) which are currently easy to buy. The wider design needs other struts, our prototype did not bend correctly so the sheet was inpossible to get on (again, 0.8 mm). We do not want to encourage you to use laser printer A4 clear sheets or laminating film! Users reported that you get headaches and vertigo after longer use. Also you cannot work on small things (dentist, stitch a wound). Especially the laminating film has bad optical properties. Further, production of injection molded parts for the original Prusa design is ramping up and sheets for the Prusa design will become common by then. Other hole layouts would be incompatible. Lastly, we found that a 297 mm wide sheet from 0.8 mm PETG is too heavy and uncomfortable. I hope these are enough reasons to not make a A4/888 version.

Q: Wie weiss ich dass mein Druck stabil genug ist?

A: Schau dir das [Quality Control](quality_control.md) Dokument an, wir zeigen ein paar Hinweise wie das Teil aussehen sollte und wie nicht.

Q: I glaube mein Teil hat den Qualitätstest nicht bestanden, was kann ich tun??

A: Das [Quality Control](quality_control.md) Document gibt auch Hinweise was man ändern kann, Schau es Dir nochmal an.

## Welches Modell soll ich drucken?

Dieses Repository enthält mehrere Modelle aus denen Du wählen kannst. Ich stelle sie hier vor:

### `stl/covid19_headband_rc3_no_text v1.stl`
Das ist ein Remix des original [Prusa Face Shield RC3](https://www.prusaprinters.org/prints/25857-prusa-face-shield). Ich habe die Texte und Einkerbungen entfernt, da sie die Druckzeit erhöhen. Darüberhinaus ist es exakt gleich mit dem Original.


### `stl/Covid-19 Shield v18.stl` und `stl/Covid-19 Shield v10.stl`
Das sind die von mir erstellten Versionen. Alle relevanten Teile haben die selbe Geometrie und Abmessungen wie das Original. Ich habe aber die Wandstärke von 2.5 auf 1.67 mm verringert. Das ermöglicht einen sehr schnellen Druck, macht das Teil aber auch etwas flexibler. Aber vielleicht ist das ja auch kein Nachteil. Der Guide im Folgenden bezieht sich auf dieses Modell.

Wenn Du Probleme mit Druckbetthaftung hast, probiere `stl/Covid-19 Shield v18 Lily.stl`. Es hat lily pads an kritischen Stellen um die Haftung auf dem Druckbett zu erhöhen. Entferne sie mit einem Seitenschneider nach dem Druck.

Wenn Du über längere Zeit z.B. über Nacht drucken willst, kannst du die gestapelten Versionen ausprobieren. Im Ordner `stl/stacks` haben wir Stapel von 2 bis 9 Teilen. Fange mit einem kleinen Stapel an und schau ob es auf deinem Drucker gut augedruckt wird und teilbar ist!

**ACHTUNG: Stelle sicher dass die beiden Konturlinien gut zusammenhaften! Wenn sie das nicht tun, wird das fertige Teil extrem schwach sein! Du kannst versuchen die Extrusionsbreite noch weiter zu erhöhen (z.B. auf 1mm) oder den Extrusionsfaktor erhöhen. Wenn die Konturenhaftung weiterhin nicht hält, durcke das Modell v10 oder die originale RC3!**

### `stl/Covid-19 Shield 2.5mm v2.stl`
Wenn Dir die obere Variante zu flexibel ist, kannst Du diese Variante ausprobieren. Sie hat die selbe Stärke wie das original von Prusa. Es hat eine konstante Wandstärke von 2.5 mm.

Anmerkung: Dies ist eine stabilere Variante der `v10`. Ich werde keine stabile Variante der `v18` erstellen, da die `v18` stabil genug ist.

### `stl/Bottom Reinforcement fast MK2 v3.stl`
Dies ist eine optimierte Version des original der unteren Verstärkung des Prusa Schilds. Es hat keine Löcher und ebenfalls eine konstante Wandstärke von 1.67 mm. Das Original hat einen 1 mm Spalt für die Plastikfolie, diese Variante hat einen 0.8mm Spalt für einen festeren Sitz. Stelle sicher dass deine Plastikfolie passt bevor du die Massenproduktion startest!

### `stl/Bottom Reinforcement light v10.stl`
Diese Alternative zur originalen unteren Verstärkung lässt sich wesentlich schneller drucken. (Ich schaffe 20 Stück in 53 Minuten). Es funktioniert mit allen Folienstärken, 0.25mm, 0.5mm, und 0.75mm sind bereits erfolgreich gestestet worden. Wenn Du dir unsicher bist welches Unterteil du drucken willst, dann nimm dieses!

Danke an Hackbroetchen für die Idee in seinem Original design: https://www.prusaprinters.org/prints/27801-easy-and-fast-bottom_reinforcement-alternative

## Druck Einstellungen

Grundsätzlich ist das Modell das wir drucken wollen recht einfach. Es muss nicht super schön aussehen, es muss nur funktional sein. Die Geschwindigkeit wird grundsätzlich durch einen einzigen Parameter bestimmt: `Maximale Volumengeschwindigkeit`. Dieser Parameter ist in `mm³/s` (kubikmillimeter pro Sekunde) angegeben uns sagt `PrusaSlicer` wieviel Filament das Hotend maximal pro Sekunde schmelzen kann. Der genau Wert hängt ab vom hotend, dem Düsendurchmesser, dem Material, der Düsentemperatur, der Extrudermechanik, etc... also musst Du etwas experimentieren um die beste Einstellung zu finden. Am Ende läuft es auf folgendes hinaus: Du willst dass der Drucker das Maximum an Material ausdruckt und zwar in _jedem Moment_. Glücklicherweise ist dazu nicht zwingend eine große Düse nötig (aber es hilft). Auch Drucker mit 0.4mm Düse können Ihre `Maximale Volumengeschwindigkeit` erreichen.

Es gibt einige Features die Deinen Drucker langsamer machen. Dazu gehören Lückenfüllungen in kleinen Spalten zwischen Konturlinien oder kleinen Löchern, scharfe Änderungen der Druckrichtung und Infill (das quasi ständig scharfe Richtungsänderungen erfordert). Wenn Du es schaffst Dein Modell nur aus Konturlinien zu drucken, kannst Du die Druckgeschwindigkeit stark erhöhen!

Das folgende Bild zeigt Infill (Dunkelrot) und Lückenfüllungen (Weiß). Beide verlandsamen den Druck.
![Gap Fill and Infill][gap_fill_and_infill]

Das folgende Bild zeigt ein Modell dass nur aus einer einzigen Konturlinie besteht, die einmal um das ganze Teil läuft (was zwei parallele Konturlien erzeugt). Das ist sehr viel schneller druckbar (und ergibt auch eine sehr schöne Oberfläche).
![Only Perimeters][only_perimeters]

Wie kann man das erreichen?

Zuerst braucht man ein Modell mit einer genau bekannten und konstanten Wandstärke. Das Modell `stl/Covid-19 Shield v18.stl` ist so erstellt dass die Wandstärke überall 1.67 mm beträgt. Wenn sich die Breiten der Konturlinien auf exakt 1.67 mm addieren dann wird kein Infill und keine Lückenfüllung mehr benötigt.

Zweitens muss die Extrusionsbreite korrekt eingestrellt werden. Zum Glück kann `PrusaSlicer` dabei helfen. Es gibt eine Funktion die die optimale Wandstärke für dünne Wände anzeigt:
![Thin Wall Thickness][thin_wall_thickness]

Hier wird die optimale Stärke für dünne Wände mit 1.68 mm für zwei Linien und 3.29 mm für 4 Linien angegeben. 1.68 mm ist sehr nah an 1.67mm, also haben wir mit 1.67 mm die richtige Einstellung! Dieser Wert hängt von der `Schichtdicke` und der Extrusionsbreite für `Konturlinien` und `Außenkonturen` ab. Eine Extrusionsbreite von 0.87 mm und eine Schichthöhe von 0.3 mm werden hier für eine 0.4 mm Düse verwendet. Ja, man kann tatsächlich 0.87 mm breite Linien mit einer 0.4 mm Düse drucken (zumindest mit einer E3D Düse). Dieses [YouTube video by CNCKitchen](https://www.youtube.com/watch?v=9YaJ0wSKKHA) gibt mehr Hintergrund dazu, wenn es Dich interessiert.

Ok, jetzt haben wir ein Modell dass für diese Art zu Drucken optimiert ist und die passende Konturlinienbreite. Sprechen wir nun über Druckgeschwindigkeit. Erinnerst Du Dich an die `Maximale Volumengeschwindigkeit`? Das ist Deine Druckgeschwindigkeit. etze alle Geschwindigkeiten (abgesehen von `Stützstrukturen`, `Überbrückungen`, `Lückenfüllung`, und `Geschwindigkeit der ersten Schicht`) auf Deine `Eilgang` Geschwindigkeit. Ja, mach das. Du wirst diese Bewegungsgeschwindigkeit sowiso nicht erreichen (solltest Du die Geschwindigkeit doch erreichen: Kann ich bitte deinen Drucker haben?). Nun stelle die `Maximale Volumengeschwindigkeit` in `Filament Einstellungen/Erweiterte Einstellungen` auf einen niedrigen Startwert. 8 mm³/s ist für den Anfang ein guter Wert.

Lass uns nun einige andere Einstellungen durchgehen, die deine Druckgeschwindigkeit erhöhen können: Das Modell das wir drucken benötigt keinen Infill. Du kannst Infill getrost auf 0% setzen. Nur die Haken für das Gummiband würden etwas Infill bekommen und kommen auch gut ohne aus. Außerdem kannst du Lückenfüllungen komplett abschalten. Ja, dabei entstehen kleine Löcher, aber es spart Einiges an Zeit und könnte auch das Fädenziehen(Stringing) reduzieren, da das Füllmaterial manchmal nicht vollständig in die Lücke passt und hervorquillt. Schalte Lückenfüllungen durch setzten der `Lückenfüllungen` Geschwindigkeit auf 0.

Nun gehe zum `Druckplatte` Tab und slice Dein Modell. In der linken unteren Ecke, schalte die `Ansicht` auf `Volumetrische Flussrate`. Dein Modell sollte abgesehen von der ersten Schicht überall die maximale Flussrate (8 mm³/s) wie in diesem Bild haben:
![Flow Rate][flow_rate]

Du solltest nun bereit sein für Deinen ersten Test mit hoher Geschwindigkeit. Wenn das gut funktioniert (und ich hoffe dass es das tut und dieser Guide kein Mist ist..) kannst Du die `Maximale Volumengeschwindigkeit` (z.B. in Schritten von 2 mm³/s) erhöhen bis dein Druck anfängt mies auszusehen oder der Extruder schmerzhafte Geräsche von sich gibt und Schritte verliert. Wenn das passiert, hast Du das Limit deines Druckers erreicht. Gehe zurück zum letzten funktionierenden Wert (Ich lasse meinen Prusa i3 MK2.5S mit a 0.8 mm Düse bei 17 mm³/s laufen).

## Fortgeschrittene Parameter Einstellungen

Ok, du hast den Druck grundsätzlich schnell laufen, aber Du willst Mehr!

Du kannst bei `Schichten und Umfängen` die Anzahl der `Massive Schichten` an der Decke erhöhen um die Löcher im der obersten Schicht der Haken für das Gummiband zu schliessen. Setze die Anzahl für `Massive Schichten` auf 5. Es hilft außerdem in den Erweiterten Einstellungen `Massives Infill` und `Oberes massives Infill` auf 0.55 mm zu setzen um noch mehr Löcher zu schließen.

Du kannst außerdem den K Faktor deines Druckers feineinstellen (auch bekannt als linear advance). Stelle sicher dass der Drucker das unterstützt. Prusa drucker tun dies. Der Faktor kontrolliert praktisch den Druck in der Düse. Das ist besonders bei hohen Geschwindigkeiten wichtig. Du kannst mehr darüber in diesem Prusa Knowledge Base Artikel lesen [Prusa Knowledge Base](https://help.prusa3d.com/en/article/linear-advance_2252). Prusa empfiehlt einen Standardwert von 45 für PETG. Ich bekomme bessere Ergebnisse mit 40 bei einer 0.4 mm Düse. Mit meiner 0.8 mm Düse nutze ich aktuell einen Wert von 15.

[gap_fill_and_infill]: pictures/gap_fill_and_infill.PNG "Gap Fill and Infill"

[only_perimeters]: pictures/only_perimeters.PNG "Only Perimeters"

[thin_wall_thickness]: pictures/thin_wall_thickness.PNG "Thin Wall Thickness"

[flow_rate]: pictures/flow_rate.PNG "Flow Rate"
