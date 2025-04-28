<!--
Meta Description: # PROC SORT in SAS: Daten effizient sortieren ## Synopsis PROC SORT ist ein grundlegender SAS-Befehl, mit dem Datensätze in einer SAS-Datenbank oder e...
Meta Keywords: proc, sort, die, sas, der
-->

# PROC SORT in SAS: Daten effizient sortieren

## Synopsis
PROC SORT ist ein grundlegender SAS-Befehl, mit dem Datensätze in einer SAS-Datenbank oder einem Datensatz alphabetisch oder numerisch sortiert werden. Dieser Befehl ist entscheidend für die Datenorganisation und -analyse.

## Documentation
### Zweck
PROC SORT wird verwendet, um Datensätze in aufsteigender oder absteigender Reihenfolge basierend auf einem oder mehreren Variablen zu sortieren. Dies ist besonders nützlich, wenn Daten analysiert oder Berichte erstellt werden sollen, die eine bestimmte Reihenfolge erfordern.

### Verwendung
Der grundlegende Syntax für PROC SORT ist wie folgt:

```sas
PROC SORT DATA=<Datenquelle> OUT=<Ausgabedaten>;
   BY <Sortiervariablen>;
RUN;
```

- **DATA=<Datenquelle>**: Gibt den Namen des Eingabedatensatzes an, der sortiert werden soll.
- **OUT=<Ausgabedaten>**: (Optional) Der Name des neuen sortierten Datensatzes. Wenn dieser Parameter nicht angegeben wird, wird der ursprüngliche Datensatz überschrieben.
- **BY <Sortiervariablen>**: Bestimmt die Variablen, nach denen die Daten sortiert werden sollen. Mehrere Variablen können durch Leerzeichen getrennt angegeben werden.

### Details
- Standardmäßig wird eine aufsteigende Sortierung durchgeführt. Um eine absteigende Sortierung für eine bestimmte Variable zu erreichen, kann das Keyword `DESCENDING` verwendet werden.
- PROC SORT entfernt standardmäßig Duplikate, es sei denn, die Option `NODUPKEY` wird verwendet.

## Examples
### Beispiel 1: Einfache Sortierung
```sas
DATA beispiel;
   INPUT name $ alter;
   DATALINES;
   Max 30
   Anna 25
   Peter 28
   ;
RUN;

PROC SORT DATA=beispiel OUT=sortiert;
   BY name;
RUN;
```

### Beispiel 2: Sortierung mit mehreren Variablen
```sas
DATA beispiel;
   INPUT name $ alter geschlecht $;
   DATALINES;
   Max 30 M
   Anna 25 F
   Peter 28 M
   Anna 22 F
   ;
RUN;

PROC SORT DATA=beispiel OUT=sortiert;
   BY geschlecht alter;
RUN;
```

### Beispiel 3: Absteigende Sortierung
```sas
PROC SORT DATA=beispiel OUT=sortiert;
   BY DESCENDING alter;
RUN;
```

## Explanation
Ein häufiger Fehler bei der Verwendung von PROC SORT ist, die Sortierreihenfolge nicht korrekt anzugeben, was zu unerwarteten Ergebnissen führen kann. Es ist auch wichtig, sich der Auswirkungen bewusst zu sein, die die Verwendung von `OUT=` auf den ursprünglichen Datensatz hat, falls dieser nicht beibehalten werden soll. Darüber hinaus kann das Fehlen der `BY`-Anweisung dazu führen, dass der Befehl nicht funktioniert oder die falsche Sortierung erfolgt.

## One Line Summary
PROC SORT in SAS ermöglicht es Benutzern, Datensätze effizient nach einer oder mehreren Variablen zu sortieren, um die Datenanalyse zu erleichtern.