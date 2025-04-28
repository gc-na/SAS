<!--
Meta Description: # SET-Befehl in SAS: Grundlagen und Anwendung ## Synopsis Der SET-Befehl in SAS ist ein grundlegender Bestandteil der Datenmanipulation, der es ermögl...
Meta Keywords: der, set, die, befehl, sas
-->

# SET-Befehl in SAS: Grundlagen und Anwendung

## Synopsis
Der SET-Befehl in SAS ist ein grundlegender Bestandteil der Datenmanipulation, der es ermöglicht, Datensätze aus einem oder mehreren Datensätzen zu lesen und in eine neue Datenanwendung zu integrieren.

## Dokumentation
Der SET-Befehl wird in einem DATA-Schritt verwendet, um Daten aus vorhandenen SAS-Datensätzen auszulesen. Er ist besonders nützlich, wenn man mehrere Datensätze zusammenführen oder Daten nach bestimmten Kriterien filtern möchte. Der Befehl kann auch in Kombination mit anderen SAS-Funktionen und -Befehlen verwendet werden, um komplexe Datenmanipulationen durchzuführen.

### Verwendung
Die grundlegende Syntax des SET-Befehls lautet:
```sas
DATA neuer_datensatz;
    SET vorhandener_datensatz;
RUN;
```
Hierbei ist `neuer_datensatz` der Name des Datensatzes, der erstellt wird, und `vorhandener_datensatz` der Name des Datensatzes, aus dem die Daten gelesen werden.

### Details
- Der SET-Befehl kann mehrere Datensätze gleichzeitig verarbeiten, indem Sie die Namen der Datensätze durch Leerzeichen trennen.
- Er kann auch in Verbindung mit Bedingungen verwendet werden, um nur bestimmte Beobachtungen auszuwählen.
- Der SET-Befehl behält die Reihenfolge der Beobachtungen bei, wie sie im ursprünglichen Datensatz erscheinen.

## Beispiele
### Beispiel 1: Einfacher SET-Befehl
```sas
DATA neuer_datensatz;
    SET vorhandener_datensatz;
RUN;
```
In diesem Beispiel wird ein neuer Datensatz erstellt, der alle Beobachtungen aus `vorhandener_datensatz` enthält.

### Beispiel 2: SET mit mehreren Datensätzen
```sas
DATA gesamter_datensatz;
    SET datensatz1 datensatz2;
RUN;
```
Hier werden die Beobachtungen aus `datensatz1` und `datensatz2` in `gesamter_datensatz` kombiniert.

### Beispiel 3: SET mit einer WHERE-Bedingung
```sas
DATA gefilterter_datensatz;
    SET vorhandener_datensatz;
    WHERE variable = 'Bedingung';
RUN;
```
In diesem Beispiel werden nur die Beobachtungen, die der Bedingung entsprechen, in `gefilterter_datensatz` aufgenommen.

## Erklärung
Ein häufiger Fehler beim Einsatz des SET-Befehls ist, dass Benutzer nicht beachten, dass der SET-Befehl die Originaldaten nicht verändert, sondern nur eine Kopie der Daten erstellt. Ein weiterer Stolperstein kann sein, dass bei der Verwendung mehrerer Datensätze die Reihenfolge der Datensätze die Reihenfolge der Beobachtungen im neuen Datensatz beeinflusst. 

Ein zusätzlicher Hinweis ist, dass der SET-Befehl nicht für die Verarbeitung von externen Datenquellen geeignet ist. Um Daten aus externen Quellen zu importieren, sollten andere SAS-Befehle wie `PROC IMPORT` verwendet werden.

## Ein-Satz-Zusammenfassung
Der SET-Befehl in SAS ermöglicht das effiziente Lesen und Kombinieren von Datensätzen im Rahmen der Datenmanipulation.