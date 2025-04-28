<!--
Meta Description: # MERGE in SAS: Daten zusammenführen für effektive Analysen ## Synopsis Der MERGE-Befehl in SAS ermöglicht es Benutzern, mehrere Datensätze basierend ...
Meta Keywords: die, merge, data, run, der
-->

# MERGE in SAS: Daten zusammenführen für effektive Analysen

## Synopsis
Der MERGE-Befehl in SAS ermöglicht es Benutzern, mehrere Datensätze basierend auf gemeinsamen Variablen zu kombinieren. Diese Funktion ist besonders nützlich für die Datenanalyse, wenn Informationen aus verschiedenen Quellen in einem einzigen Datensatz konsolidiert werden müssen.

## Dokumentation
### Zweck
Der MERGE-Befehl wird verwendet, um zwei oder mehr SAS-Datensätze zusammenzuführen, wobei die Zusammenführung auf einem oder mehreren gemeinsamen Schlüsselvariablen basiert. Dies ist entscheidend für die Erstellung umfassender Datenbanken, die verschiedene Aspekte eines Themas abdecken.

### Verwendung
Um den MERGE-Befehl zu verwenden, müssen die Datensätze, die zusammengeführt werden sollen, zunächst nach den Schlüsselvariablen sortiert werden. Die Grundsyntax für den MERGE-Befehl lautet:

```sas
DATA neuer_datensatz;
    MERGE datensatz1 datensatz2;
    BY gemeinsame_variable;
RUN;
```

### Details
- **Gemeinsame Variablen**: Diese müssen in beiden Datensätzen vorhanden sein und denselben Namen haben.
- **Sortierung**: Vor der Verwendung von MERGE müssen die Datensätze nach den gemeinsamen Variablen sortiert werden.
- **Fehlende Werte**: Wenn für eine gemeinsame Variable in einem der Datensätze kein Wert vorhanden ist, wird der entsprechende Datensatz nicht in das Ergebnis übernommen.

## Beispiele

### Beispiel 1: Einfaches Zusammenführen
```sas
DATA kunden;
    INPUT kunden_id name $;
    DATALINES;
1 Max
2 Lisa
3 Tom
;
RUN;

DATA bestellungen;
    INPUT kunden_id bestellnummer;
    DATALINES;
1 1001
2 1002
3 1003
;
RUN;

DATA kunden_bestellungen;
    MERGE kunden bestellungen;
    BY kunden_id;
RUN;

PROC PRINT DATA=kunden_bestellungen; 
RUN;
```

### Beispiel 2: Zusammenführen mit fehlenden Werten
```sas
DATA kunden;
    INPUT kunden_id name $;
    DATALINES;
1 Max
2 Lisa
;
RUN;

DATA bestellungen;
    INPUT kunden_id bestellnummer;
    DATALINES;
1 1001
3 1003
;
RUN;

DATA kunden_bestellungen;
    MERGE kunden bestellungen;
    BY kunden_id;
RUN;

PROC PRINT DATA=kunden_bestellungen; 
RUN;
```

## Erklärung
Ein häufiges Problem beim MERGE-Befehl ist die Notwendigkeit, sicherzustellen, dass die Datensätze korrekt sortiert sind. Wenn diese Anforderung nicht erfüllt ist, kann es zu unerwarteten Ergebnissen kommen. Außerdem sollten Benutzer darauf achten, dass die gemeinsamen Variablen in beiden Datensätzen vorhanden sind, da fehlende Variablen zu Fehlern führen können.

Ein weiterer wichtiger Punkt ist, dass wenn in einem der Datensätze ein Wert fehlt, die entsprechenden Zeilen nicht im Ergebnis erscheinen. Dies kann bei der Analyse zu Verwirrung führen, insbesondere wenn Benutzer erwarten, dass alle Kunden angezeigt werden, auch wenn sie keine Bestellungen aufgegeben haben.

## Ein-Satz-Zusammenfassung
Der MERGE-Befehl in SAS ist ein effektives Werkzeug zum Zusammenführen von Datensätzen basierend auf gemeinsamen Variablen, um eine umfassendere Datenbasis für die Analyse zu schaffen.