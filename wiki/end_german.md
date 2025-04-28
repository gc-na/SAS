<!--
Meta Description: # END in SAS: Befehle und Anwendungen ## Synopsis Der Befehl "END" in SAS wird verwendet, um das Ende einer DO-Schleife oder einer Datenstufe zu kennz...
Meta Keywords: end, der, schleife, die, sas
-->

# END in SAS: Befehle und Anwendungen

## Synopsis
Der Befehl "END" in SAS wird verwendet, um das Ende einer DO-Schleife oder einer Datenstufe zu kennzeichnen. Es ist ein entscheidendes Element zur Strukturierung von SAS-Programmen und zur Steuerung des Programmflusses.

## Dokumentation
### Zweck
Der Befehl "END" ist Teil der SAS-Syntax und wird typischerweise verwendet, um das Ende einer DO-Schleife zu markieren. DO-Schleifen sind nützlich, um wiederholende Aufgaben zu automatisieren und die Programmierung effizienter zu gestalten.

### Verwendung
Der Befehl "END" wird in Kombination mit der DO-Anweisung verwendet. Er signalisiert den Abschluss eines Codeblocks, der innerhalb einer Schleife ausgeführt wird. In Kombination mit der IF-Anweisung kann "END" auch verwendet werden, um Bedingungen innerhalb von Schleifen zu steuern.

### Details
- **Syntax**: 
  ```sas
  DO i = 1 TO n;
    /* Anweisungen */
  END;
  ```
- "n" ist eine numerische Variable, die angibt, wie oft die Schleife durchlaufen wird.
- Der Befehl "END" ist zwingend erforderlich, um die DO-Schleife korrekt zu schließen.

## Beispiele
### Beispiel 1: Einfache DO-Schleife
```sas
data test;
  do i = 1 to 5;
    output;
  end;
run;
```
In diesem Beispiel wird eine DO-Schleife erstellt, die fünf Iterationen durchläuft und in jeder Iteration einen Datensatz ausgibt.

### Beispiel 2: DO-Schleife mit IF-Anweisung
```sas
data test;
  do i = 1 to 10;
    if mod(i, 2) = 0 then
      output;
  end;
run;
```
Hier gibt die Schleife nur gerade Zahlen aus. Der Befehl "END" schließt die DO-Schleife ab.

## Erklärung
Eine häufige Fallstrick sind nicht korrekt geschlossene DO-Schleifen, die zu Fehlern in der Ausführung führen können. Es ist wichtig, sicherzustellen, dass jede DO-Anweisung mit einem entsprechenden "END" abgeschlossen wird. Eine andere häufige Herausforderung ist das Missverständnis bei der Verwendung von "END" in Verbindung mit anderen Steueranweisungen, wie z. B. IF oder SELECT, die ebenfalls ihre eigenen End-Anweisungen benötigen.

## Einzeiler Zusammenfassung
Der Befehl "END" in SAS markiert das Ende einer DO-Schleife und ist entscheidend für die korrekte Programmstruktur und -ausführung.