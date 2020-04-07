# Qualitätskontrolle für das Behelfs Gesichtsschild

Willkommen zur Qualitäts-Sektion! Dass Du hier bist, zeigt dass dich auch interessiert was Du druckst. Herzlichen Glückwunsch!

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

Biege die beiden Enden übereinander:
![Bend 5][bend5]

[Hier](https://cloud.stratum0.org/index.php/s/fAjpCAXFLmFsxLq?path=%2FMaterialtest%20Videos) gibt es ein Video das zeigt wie ein PLA Teil misshandelt werden kann, wenn es korrekt gedruckt ist. (file `PLA biegen.mp4`).

## Wie dein Teil nicht aussehen sollte

[Hier](https://cloud.stratum0.org/index.php/s/fAjpCAXFLmFsxLq?path=%2FMaterialtest%20Videos) ist ein Video das ein guten mit einem schlechten Teil vergleicht (file `qualitätstest.MOV`).

### Lücken

Dieses Teil hat Lücken (siehe bei den beiden oberen roten Pfeile) was zum bröseln im video oben führt:
![Gaps][gaps]

Es gibt zwei Möglichkeiten die Lücken zu schließen: Im `PrusaSlicer` kannst Du die `Extrusionsbreite` der `External perimeters` noch weiter erhöhen (über 0.87 mm). `PrusaSlicer` wird die beiden Hüllen näher zusammenbringen (um die erforderliche Wandstärke von 1.67 mm zu erreichen). Die andere Option ist den `Extrusion multiplier` zu erhöhen und so mehr Material zu verdrucken was dann die Lücken schliessen kann.

Das Problem an den unteren beiden roten Pfeilen kann durch Verringern der `Extrusionsbreite` für `Solid infill` und `Top solid infill` auf 0.55 mm oder weniger (abhängig von Deinem Düsendurchmesser) behoben werden.

### Löcher

Du könntest auch Löcher in Deinem Teil haben:
![Holes][holes]

This effect can be reduced by increasing the `Extrusion width` of `External perimeters`. I found 1.0 mm working.
Dieser Effekt kann durch verringern der `Extrusionsbreite` von `External perimeters` verbessert werden. Bei mir funktioniert ein Wert von 1.0.
[Bend1]: pictures/bend1.jpg "Bend 1"
[Bend2]: pictures/bend2.jpg "Bend 2"
[Bend3]: pictures/bend3.jpg "Bend 3"
[Bend4]: pictures/bend4.jpg "Bend 4"
[Bend5]: pictures/bend5.jpg "Bend 5"
[Gaps]: pictures/gaps.jpg "Gaps"
[Holes]: pictures/holes.jpg "Holes"
