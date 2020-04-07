# Qualitätskontrolle für das Behelfs Gesichtsschild

Willkommen zur Qualitäts-Sektion! Dass Du hier bist, zeigt dass du dich auch interessiert was Du druckst. Herzlichen Glückwunsch!

**ACHTUNG: Diese Tests gelten nur für die `v18` Version! Andere Versionen sind nicht so flexibel und werden eher brechen!**

## Wie dein Teil aussehen sollte

Wir wissen nicht, was dein Teil wirklich aushalten muss. Wir können Dir nur zeigen was unsere Teile aushalten. Wenn Deine Teile eher brechen, heißt das nicht unbedingt dass sie schlecht sind, es heißt nur dass sie nicht so gut sind wie sie sein könnten! **Unser Teil in den Bildern ist aus PETG, wenn Du in anderem Material gedruckt hast, können die Ergebnisse abweichen.**

Um dein teil zu prüfen, biege es wie im folgenden gezeigt. **Es sollte dabei absolut nicht brechen!**

Lege dein Teil auf den Tisch und drücke die Enden für die Plastikfolie nach Unten:
![Bend 1][bend1]

Biege die Enden für das Gummiband zusammen:
![Bend 2][bend2]

Verdrehe die beiden Seiten im Winekel von 90° gegeneinander **mehrfach in beide Richtungen**:
![Bend 3][bend3]
![Bend 4][bend4]

Bend the two sides across each other:
![Bend 5][bend5]

[Here](https://cloud.stratum0.org/index.php/s/fAjpCAXFLmFsxLq?path=%2FMaterialtest%20Videos) you can find a video that shows how a PLA part can be abused if printed properly (file `PLA biegen.mp4`).

## What your part should not look like

[Here](https://cloud.stratum0.org/index.php/s/fAjpCAXFLmFsxLq?path=%2FMaterialtest%20Videos) you can find a video that shows how a good part looks in comparison to a bad part (file `qualitätstest.MOV`).

### Gaps

This part contains gaps (top two red arrows) which lead to the crumbling in the video shown above:
![Gaps][gaps]

You have two options to close these gaps: In `PrusaSlicer` you can increase the `Extrusion width` of `External perimeters` even more (above 0.87 mm). `PrusaSlicer` will put the two shells closer together in this case (to reach the required 1.67 mm wall thickness). The other option is to increase the `Extrusion multiplier` so more material can fill the gap.

The problem indicated by the lower red arrow can be fixed by decreasing the `Extrusion width` for `Solid infill` and `Top solid infill` to 0.55 mm or less, depending on your nozzle size.

### Holes

You might also encounter holes in your part:
![Holes][holes]

This effect can be reduced by increasing the `Extrusion width` of `External perimeters`. I found 1.0 mm working.

[bend1]: pictures/bend1.jpg "Bend 1"
[bend2]: pictures/bend2.jpg "Bend 2"
[bend3]: pictures/bend3.jpg "Bend 3"
[bend4]: pictures/bend4.jpg "Bend 4"
[bend5]: pictures/bend5.jpg "Bend 5"
[gaps]: pictures/gaps.jpg "Gaps"
[holes]: pictures/holes.jpg "Holes"
