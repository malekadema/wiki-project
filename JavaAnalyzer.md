# Java Analyzer

## Einleitung

Bei dem Programm handelt es sich um einen Scanner der das entsprechende Ziel nach Java Installationen absucht und daraus einen detaillierten Bericht mit Pfad zur Datei erstellt.

## Vorraussetzungen

Windows 64Bit

## Hauptteil

### Nutzen und Bedarf

wir muessen gegenueber Oracle beweisen, dass wir keine lizenzpflichtigen Java Produkte einsetzen. Deshalb scannen wir exemplarisch PCs aus verschiedenen Abteilungen nach Java installationen um zu beweisen, dass wir nur Open Source Versionen nutzen. Falls wir dabei lizenzpflichtige Produke finden, muessen wir weiter entscheiden was wir damit machen.

### Funktion

das Programm scannt die MFT nach java.exe und javac.exe Dateien ab. Bei einem Fund werden die wichtigen Daten ProductName, ProductVersion und SignerName ausgelesen. Letzteres zeigt, ob es sich um eine lizenzpflichtige Version handelt. Diese Daten werden nach beendigung ausgegeben und in eine Datei geschrieben.

### Vorbereitung

Am sinnvolsten ist es das Tool auf eine Netzwerkfreigabe zu legen, damit dort auch die Scan Resultate gesammelt an einem Ort liegen.
Das Programm sollte mit Administrator Rechten ausgefuehrt werden, damit es zuverlaessig auch die /Users Ordner scannen kann.

### Ausfuehrung

- auf dem ensprechenden PC den Netzwerkspeicherort des Programmes oeffnen
- Programm mit Administratorrechten ausfuehren
- der Scan scannt automatisch Laufwerk C:/. Falls eine weiterer Speicherort gescannt werden soll, muss dies ueber die Parameter im naechsten Abschnitt angegeben werden.
- das Programm oeffnet ein Eingabeaufforderungsfenster. Jede 5000. gescannte Datei wird angezeigt
    - falls Fehler auftreten, werden sie angezeigt
    - ansonsten werden nur die gescannten Dateien angezeigt
- wenn das Programm durchgelaufen ist, wird das Ergebnis angezeigt
- ausserdem wird im Programmpfad eine Datei angelegt mit dem Muster JavaAnalyzer.outputPCNameLaufwerkTimestamp.json

### Parameter

| Parameter | Beispiel | Ergebnis |
| --- | --- | --- |
| partition:\ | JavaAnalyzer.exe d:\ | Die Festplatte D:\ wird gescannt. |
| "partition:\ordner" | JavaAnalyzer.exe „d:\folder with spaces“ | der angegebene Pfad wird gescannt. |

### Fehlervermeidung

Damit alle Teile der Festplatte untersucht werden koennen sollte das Programm als Administrator ausgefuehrt werden.
