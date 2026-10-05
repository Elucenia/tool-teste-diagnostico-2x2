<!-- ELUCENIA technical documentation · teste-diagnostico-2x2 · de · no clinical/professional/rights approval -->

# Diagnostischer Test (2×2-Tabelle)

[Bedingungen, Quellen und Berechtigungen](https://elucenia.org/de/werkzeuge/teste-diagnostico-2x2)

## Verwendung

Verwenden Sie das Werkzeug im Portal oder öffnen Sie index.html über einen lokalen HTTP-Server. Wählen Sie die Sprache, füllen Sie die Felder aus und berechnen Sie das Ergebnis.

## Eingaben und Einheiten

### Richtig positive (RP): positiver Test und Erkrankung vorhanden

`vp`

Bereich: 0–1000000

### Falsch positive (FP): positiver Test und keine Erkrankung

`fp`

Bereich: 0–1000000

### Falsch negative (FN): negativer Test und Erkrankung vorhanden

`fn`

Bereich: 0–1000000

### Richtig negative (RN): negativer Test und keine Erkrankung

`vn`

Bereich: 0–1000000

## Fassung der Methode

2×2:Sensitivität/Spezifität/PPV/NPV; Wilson 95% Anteile; Simel 1991 Log-LR-KI; kein Wald

## Dokumentierte Formel

Sensitivität = TP / (TP + FN) · Spezifität = TN / (TN + FP) · PPV = TP / (TP + FP) · NPV = TN / (TN + FN) · Genauigkeit = (TP + TN) / Gesamt.

LR+ = Sensitivität / (1 − Spezifität) · LR− = (1 − Sensitivität) / Spezifität.

95%-KI: Wilson-Score für Anteile; logarithmische Methode für Likelihood-Quotienten (Simel 1991), SE(ln LR+) = √(1/TP − 1/(TP+FN) + 1/FP − 1/(FP+TN)).

## Grenzen und Population

Die Tabelle erfordert eine binäre Einteilung des Tests und des Referenzstatus mit konsistenten Häufigkeiten für dieselbe Population. Positive und negative prädiktive Werte hängen von der Prävalenz ab und sind nicht automatisch auf eine andere Population übertragbar. Ein Nenner von null kann ein Maß undefiniert machen. Wilson-Intervalle für Anteile und logarithmische Intervalle für Likelihood-Quotienten sind unterschiedliche Methoden; Nullhäufigkeiten und kleine Stichproben erfordern eine besondere Interpretation. Diese Analyse allein belegt weder die Qualität des Referenzstandards noch validiert sie den Test.

## Referenzen

- [Altman DG, Bland JM. Statistics Notes: Diagnostic tests 1: sensitivity and specificity. BMJ, 1994.](https://doi.org/10.1136/bmj.308.6943.1552)

- [Altman DG, Bland JM. Statistics Notes: Diagnostic tests 2: predictive values. BMJ, 1994.](https://doi.org/10.1136/bmj.309.6947.102)

- [Brown LD, Cai TT, DasGupta A. Interval estimation for a binomial proportion. Statistical Science, 2001.](https://doi.org/10.1214/ss/1009213286)

- [Simel DL, Samsa GP, Matchar DB. Likelihood ratios with confidence: sample size estimation for diagnostic test studies. J Clin Epidemiol, 1991.](https://doi.org/10.1016/0895-4356(91)90128-V)

- [Deeks/Altman2004](https://pmc.ncbi.nlm.nih.gov/articles/PMC478236/)

- [Brown/Cai/DasGupta2001](https://repository.upenn.edu/bitstreams/c3690c8b-efaf-485b-a984-39cfc22aae13/download)

## Technische Tests reproduzieren

Führen Sie node test.cjs im Stammverzeichnis dieses Repositorys aus, um die dokumentierten synthetischen Fälle zu wiederholen. Ursprüngliche Eingaben, erwartete Ergebnisse und Toleranzen bleiben erhalten. Technische Tests stellen keine klinische Validierung dar.

```sh
node test.cjs
```

tool.json enthält Quellen, Ausgabe und Umfang der Überprüfung. examples.json bewahrt die synthetischen Eingaben und erwarteten Ergebnisse; results.json dokumentiert die tatsächlich erhaltenen Ergebnisse.

[Eintrag und Referenzen](../tool.json) · [JavaScript-Code](../calculator.js) · [Referenzfälle](../examples.json) · [results.json](../results.json)

## Überprüfung und Nutzungsbedingungen

Eine unabhängige klinische Prüfung wurde nicht durchgeführt.

Diese Benutzeroberfläche ist eine selbst erstellte Übersetzung und keine offizielle oder zertifizierte Ausgabe. Eine unabhängige klinische Überprüfung, eine professionelle sprachliche Prüfung und eine Klärung der Rechte an den Instrumenten wurden nicht durchgeführt.

Ergebnis der Formel oder Klassifikation. Interpretation, Vorgehen und Anwendbarkeit hängen von der fachlichen Beurteilung und der ausgewählten Quelle ab.

## Lizenz und Urheberangaben

Apache-2.0 gilt nur für den ELUCENIA-Code. Die Rechte an Instrumenten, Veröffentlichungen, Übersetzungen und Daten verbleiben bei den jeweiligen Rechteinhabern. Bewahren Sie LICENSE und NOTICE auf.

ELUCENIA · Felipe Guedes · Copyright © 2026
