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

Q: Can you provide a 888 version for A4 sheets?

A: Short answer: Good idea, a hospital also asked us for wider shields, so we did a prototype of this. Our results were mediocre at best, thus we discarded the idea and focused on the `v18` instead. Long answer: 888 punches are not close to the edge, the sheet will not bend properly around the printed part. You could solve this with extra hooks that catch the sheet at the ends. However, this would not work with thick sheets (0.8 mm) which are currently easy to buy. The wider design needs other struts, our prototype did not bend correctly so the sheet was inpossible to get on (again, 0.8 mm). We do not want to encourage you to use laser printer A4 clear sheets or laminating film! Users reported that you get headaches and vertigo after longer use. Also you cannot work on small things (dentist, stitch a wound). Especially the laminating film has bad optical properties. Further, production of injection molded parts for the original Prusa design is ramping up and sheets for the Prusa design will become common by then. Other hole layouts would be incompatible. Lastly, we found that a 297 mm wide sheet from 0.8 mm PETG is too heavy and uncomfortable. I hope these are enough reasons to not make a A4/888 version.

Q: Wie weiss ich dass mein Druck stabil genug ist?

A: Schau dir das [Quality Control](quality_control.md) Dokument an, wir zeigen ein paar Hinweise wie das Teil aussehen sollte und wie nicht.

Q: I glaube mein Teil hat den Qualitätstest nicht bestanden, was kann ich tun??

A: Das [Quality Control](quality_control.md) Document gibt auch Hinweise was man ändern kann, Schau es Dir nochmal an.

## Welches Modell soll ich drucken?

Dieses Repository enthält mehrere Modelle aus denen Du wählen kannst. Ich stelle sie hier vor:

### `stl/covid19_headband_rc3_no_text v1.stl`
Das ist ein Remix des original [Prusa Face Shield RC3](https://www.prusaprinters.org/prints/25857-prusa-face-shield). Ich habe die Texte und Einkerbungen entfernt, da sie die Druckzeit erhöhen. Darüberhinaus ist es exakt gleich mit dem Original.


### `stl/Covid-19 Shield v18.stl` und `stl/Covid-19 Shield v10.stl`
Das sind die von mir erstellten Versionen. Alle relevanten Teile haben die selbe Geometrie und Abmessungen wie das Original. Ich habe aber die Wandstärke von 2.5 auf 1.67 mm verringert. Das ermöglicht einen sehr schnellen Druck, macht das Teil aber auch etwas flexibler. Aber vielleicht ist das ja auch kein Nachteil. Der Guide im Folgenden bezioeht sich auf dieses Modell.

Wenn Du Probleme mit Druckbetthaftung hast, probiere `stl/Covid-19 Shield v18 Lily.stl`. Es hat lily pads an kritischen Stellen um die Haftung auf dem Druckbett zu erhöhen. Entferne sie mit einem Seitenschneider nach dem Druck.

Wenn Du über längere Zeit z.B. über Nacht drucken willst, kannst du die gestapelten Versionen ausprobieren. Im Ordner `stl/stacks` haben wir Stapel von 2 bis 9 Teilen. Fange mit einem kleinen Stapel an und schau ob es auf deinem Drucker gut augedruckt wird und teilbar ist!

**ACHTUNG: Stelle sicher dass die beiden Konturlinien gut zusammenhaften! Wenn sie das nicht tun, wird das fertige Teil extrem schwach sein! Du kannst versuchen die Extrusionsbreite noch weiter zu erhöhen (z.B. auf 1mm) oder den Extrusionsfaktor erhöhen. Wenn die Konturenhaftung weiterhin nicht hält, durcke das Modell v10 oder die originale RC3!**

### `stl/Covid-19 Shield 2.5mm v2.stl`
Wenn Dir die obere Variante zu flexibel ist, kannst Du diese Variante ausprobieren. Sie hat die selbe Stärke wie das original von Prusa. Es hat eine konstante Wandstärke von 2.5 mm.

Anmerkung: Dies ist eine stabilere Variante der `v10`. Ich werde keine stabile Variante der `v18` erstellen, da die `v18` stabil genug ist.

### `stl/Bottom Reinforcement fast MK2 v3.stl`
Dies ist eine optimierte Version des original der unteren Verstärkung des Prusa Schilds. Es hat keine Löcher und ebenfalls eine konstante Wandstärke von 1.67 mm. Das original hat einen 1 mm Spalt für das Plastikschild, diese Variante hat einen 0.8mm Spalt für einen festeren Sitz. Stelle sicher dass dein Plastikvisier passt bevor du die Massenproduktion startest!

### `stl/Bottom Reinforcement light v10.stl`
Diese Alternative zur originalen unteren Verstärkung lässt sich wesentlich schneller drucken. (Ich schaffe 20 Stück in 53 Minuten). Es funktioniert mit allen Folienstärken, 0.25mm, 0.5mm, und 0.75mm sind bereits erfolgreich gestestet worden. Wenn Du dir unsicher bist welches Unterteil du drucken willst, nimm dieses!

Danke an Hackbroetchen für die Idee in seinem Original design: https://www.prusaprinters.org/prints/27801-easy-and-fast-bottom_reinforcement-alternative

## Druck Einstellungen

Overall, the model we want to print is pretty simple. We do not want it to look super nice, it needs to be functional. There is basically one parameter that limits your maximum print speed: `Max. Volumetric Speed`. This parameter is defined in `mm³/s` (cubic millimeters per second) and tells `PrusaSlicer` the maximum amount of material your hotend is able to melt per second. The exact value for this depends on your hotend, nozzle size, material, print temperature, extruder gears... So you need to experiment with this a bit. In the end it boils down to this: You want your printer to extrude the maximum amount of material _all the time_. Luckily, you don't strictly need a large nozzle to achive this (but it helps). Even printers with 0.4 mm nozzles can reach their `Max. Volumetric Speed`.

There are some types of features that slow down your 3D printer. These includes gap filling small holes (or thin spaces between narrow outer perimeters), sharp turns of the printing direction and infill (which is basically sharp turns of the printing direction all the time). If you manage to print your model by only printing perimeters you can increase your print speed a lot!

The following picture shows infill (dark red) and gap fill (white). Both are slow to print.
![Gap Fill and Infill][gap_fill_and_infill]

The following picture shows a model that only consists of a single perimeter running all around the model (creating two extrusion lines). This is much faster to print (and also gives a very nice surface!).
![Only Perimeters][only_perimeters]

How can you achive this?

First, you need a model with a constant wall width and you need to know this width. The model `stl/Covid-19 Shield v18.stl` is designed to have the exact same wall thickness of 1.67 mm everywhere. If you manage that your perimeters exactly add up to 1.67 mm, no slow gap filling or infill is needed.

Second, you need to set you extrusion width correctly. Luckily, `PrusaSlicer` can help you with this. It has a function that tells you the optimal wall thickness of your model for thin wall, see the following picture:
![Thin Wall Thickness][thin_wall_thickness]

Here it says that the optimal thin wall thickness is 1.68 mm for two lines and 3.29 mm for 4 lines. 1.68 mm is very close to 1.67mm, so this is correctly configured! This value is influenced by the `Layer height` and the extrusion width for `Perimeters` and `External perimeters`. An extrusion width of 0.87 mm and a layer height of 0.3mm are used here for a 0.4 mm nozzle. Yes, you can actually print 0.87 mm width with a 0.4 mm nozzle (at least with an E3D nozzle). This [YouTube video by CNCKitchen](https://www.youtube.com/watch?v=9YaJ0wSKKHA) gives more info if you are interested.

Ok, we now have a model that is designed for this kind of print and a correct perimeter width. Let's talk about print speed. Rembember the `Max. Volumetric Speed`? This is your print speed. Configure all speeds (except for `Support material`, `Bridges`, and `Gap fill` and `First layer speed`) to your `Travel` speed. Yes, do this. You won't reach these speeds anyway (and if you actually do, can I have your printer please?). Now set the `Max. Volumetric Speed` in `Filament Settings/Advanced` to a low starting value. 8 mm³/s is a good starting point.

Let's quickly go through some other settings that can increase your print speed: The model we are printing does not need any infill. You can safely set it to 0%. Only the hooks for the rubber band would get some and they don't need it. Also, you can disable gap filling completely. Yes, this ends up with some small holes, but saves quite some time. Also it might reduce stringing, as sometimes the gap fill material does not fit into its hole and squeezes out. Disable gap fill by setting the `Gap fill` speed to 0.

Now go to the `Plater` tab and slice your model. In the bottom left corner, change the `View` to `Volumetric flow rate`. You model should have the maxum flow rate (8 mm³/s) everywhere (expect for the first layer) like in this picture:
![Flow Rate][flow_rate]

You should now be good to go for your first test print with high speed settings. If this works well (and I hope it does, otherwise this guide might be crap...) you can increase the `Max. Volumetric Speed` (e.g. in steps of 2 mm³/s) until your print starts to look ugly or your extruder makes painful noises and loses steps. If this happens, you have reached the limit of your printer. Go down to the last working value (I am running a Prusa i3 MK2.5S with a 0.8 mm nozzle at 17 mm³/s).

## Fortgeschrittene Parameter Einstellungen

Ok, you got the basic fast print working, but you want more!

You can tune the amount of `Solid layers` at the top to close holes in the top layer of hooks for the rubber band. Increase the number of solid layers to 5. It also helps to set the `Solid infill` and `Top solid infill` to 0.55 mm, to close even more holes.

You can also tune the K factor (also known as linear advance) for your printer. Make sure it supports it. Prusa printers do support this. It will basically control the pressure in the nozzle. This is important at high speeds. You can read more about this in the [Prusa Knowledge Base](https://help.prusa3d.com/en/article/linear-advance_2252). Prusa suggest a default of 45 for PETG. I get better results with 40 on a 0.4 mm nozzle. On my 0.8 mm nozzle I am currently using a value of 15.

[gap_fill_and_infill]: pictures/gap_fill_and_infill.PNG "Gap Fill and Infill"

[only_perimeters]: pictures/only_perimeters.PNG "Only Perimeters"

[thin_wall_thickness]: pictures/thin_wall_thickness.PNG "Thin Wall Thickness"

[flow_rate]: pictures/flow_rate.PNG "Flow Rate"
