<!--
Meta Description: # PROC MEANS in SAS: Statistische Zusammenfassungen von Daten ## Synopsis PROC MEANS ist ein leistungsstarkes Verfahren in SAS, das verwendet wird, um...
Meta Keywords: proc, means, die, von, der
-->

# PROC MEANS in SAS: Statistische Zusammenfassungen von Daten

## Synopsis
PROC MEANS ist ein leistungsstarkes Verfahren in SAS, das verwendet wird, um grundlegende statistische Kennzahlen wie Mittelwert, Median, Standardabweichung und Häufigkeiten von numerischen Variablen in Datensätzen zu berechnen.

## Documentation
### Zweck
PROC MEANS dient der statistischen Analyse von Daten, indem es eine Zusammenfassung von numerischen Variablen erstellt. Es ist nützlich für die Datenexploration und zur Überprüfung der Datenqualität.

### Verwendung
Der grundlegende Syntax von PROC MEANS lautet:

```sas
PROC MEANS DATA=dataset-name <options>;
   VAR variable-list;
   CLASS class-variable;
   OUTPUT OUT=output-dataset <statistics>;
RUN;
```

- **DATA**: Gibt den Datensatz an, der analysiert werden soll.
- **VAR**: Definiert die Variablen, für die die statistischen Kennzahlen berechnet werden sollen.
- **CLASS**: Teilt die Daten in Gruppen auf, um aggregierte Statistiken innerhalb jeder Gruppe zu berechnen.
- **OUTPUT**: Ermöglicht das Speichern der Ergebnisse in einem neuen Datensatz.

### Details
PROC MEANS bietet eine Vielzahl von Optionen, um die Analyse zu steuern, darunter:

- **N** (Anzahl der Werte)
- **MEAN** (Mittelwert)
- **STD** (Standardabweichung)
- **MIN** (Minimalwert)
- **MAX** (Maximalwert)
- **MEDIAN** (Median)

Zusätzlich können Sie die Optionen `ALPHA=` zur Festlegung des Konfidenzniveaus oder `BY` zur Durchführung der Analyse nach Gruppen verwenden.

## Examples
### Grundlegendes Beispiel
```sas
DATA testdaten;
   INPUT Alter Gewicht;
   DATALINES;
   25 70
   30 80
   22 65
   35 90
   28 75
   ;
RUN;

PROC MEANS DATA=testdaten MEAN STD;
   VAR Alter Gewicht;
RUN;
```

### Klassifizierte Statistiken
```sas
DATA testdaten;
   INPUT Geschlecht $ Alter Gewicht;
   DATALINES;
   M 25 70
   W 30 80
   M 22 65
   W 35 90
   M 28 75
   ;
RUN;

PROC MEANS DATA=testdaten MEAN STD;
   CLASS Geschlecht;
   VAR Alter Gewicht;
RUN;
```

## Explanation
Ein häufiger Fehler bei der Verwendung von PROC MEANS ist das Vergessen, die CLASS-Variable zu definieren, wenn Sie statistische Kennzahlen nach Gruppen analysieren möchten. Dies kann zu unerwarteten Ergebnissen führen, da die Berechnungen dann über den gesamten Datensatz erfolgen. Achten Sie auch darauf, dass fehlende Werte (Missing Values) standardmäßig ignoriert werden, was das Ergebnis beeinflussen kann.

## One Line Summary
PROC MEANS in SAS bietet eine effiziente Möglichkeit, statistische Kennzahlen für numerische Variablen zu berechnen und ermöglicht die Analyse von Daten in Gruppen.