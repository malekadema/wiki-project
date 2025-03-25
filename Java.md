# Java

## Einleitung

Dieser Artikel soll helfen die verschiedenen versionen von Java ein einer uebersicht darzustellen um Lizenzfragen zu klaeren.

## Hauptteil

### Generelle Java Versionsuebersicht

Java wurde erstmals 1995 von Sun Microsystems veröffentlicht und hat seitdem zahlreiche Versionen durchlaufen. Die folgende Tabelle gibt einen Überblick über die wichtigsten Java-Versionen, deren Veröffentlichungsdaten sowie die jeweiligen Hersteller und Lizenzen:

| Version | release | Hersteller |
| --- | --- | --- |
| 1.0 | 23. Januar 1996 | Sun Microsystems |
| 1.1 | 19. Februar 1997 | Sun Microsystems |
| 1.2 | 8. Dezember 1998 | Sun Microsystems |
| 1.3 | 8. Mai 2000 | Sun Microsystems |
| 1.4 | 6. Februar 2002 | Sun Microsystems |
| 5.0 | 30. September 2004 | Sun Microsystems |
| 6 | 11. Dezember 2006 | Sun Microsystems |
| 7 | 28. Juli 2011 | Oracle Corporation |
| 8 | 18. Maerz 2014 | Oracle Corporation |
| 9 | 21. September 2017 | Oracle Corporation |
| 10 | 20. Maerz 2018 | Oracle Corporation |
| 11 | 25. September 2018 | Oracle Corporation |
| 12 | 19. MÃ¤rz 2019 | Oracle Corporation |
| 13 | 17. September 2019 | Oracle Corporation |
| 14 | 17. Maerz 2020 | Oracle Corporation |
| 15 | 15. September 2020 | Oracle Corporation |
| 16 | 16. Maerz 2021 | Oracle Corporation |
| 17 | 14. September 2021 | Oracle Corporation |
| 18 | 22. Maerz 2022 | Oracle Corporation |
| 19 | 20. September 2022 | Oracle Corporation |
| 20 | 21. Maerz 2023 | Oracle Corporation |
| 21 | 19. September 2023 | Oracle Corporation |

Mit der Version 6 begann Sun Microsystems, Teile des Java Development Kits (JDK) unter der GNU General Public License (GPL) zu veröffentlichen. Dies führte zur Entstehung des OpenJDK-Projekts, das die offizielle freie Implementierung der Java Platform, Standard Edition (Java SE), darstellt. OpenJDK-Versionen werden unter der GPL mit Classpath-Ausnahme veröffentlicht und von verschiedenen Unternehmen unterstützt.
[OpenJDK bei Wikipedia](https://de.wikipedia.org/wiki/OpenJDK?utm_source=chatgpt.com)

### OpenJDK

| Distribution | Anbieter | Lizenz | Kommerzielle unterstuetzung |
| --- | --- | --- | --- |
| Oracle openJDK | Oracle Corporation | GPLv2+CE | Nein |
| Oracle Java SE | Oracle Corporation | Proprietaer | Ja |
| Eclipse Temurin | Eclipse Foundation | GPLv2+CE | Optional (ueber Partner) |
| Amazon Coretto | Amazon | GPLv2+CE | Nein |
| Azul Zulu| Azul Systems | GPLv2+CE | Ja |
| BellSoft Liberica JDK | BellSoft | GPLv2+CE | Ja |
| Microsoft Build of OpenJDK | Microsoft | GPLv2+CE | Ja (fuer Azure Kunden) |
| Red Hat OpenJDK | Red Hat | GPLv2+CE | Ja |
| SAP SapMachine | SAP | GPLv2+CE | Nein |

Es ist wichtig zu beachten, dass die meisten dieser Distributionen unter der GPLv2+CE-Lizenz stehen, was die freie Nutzung und Verbreitung ermöglicht. Einige Anbieter, wie Oracle mit seiner Java SE Distribution, bieten jedoch auch proprietäre Lizenzen an, die zusätzliche kommerzielle Features und Supportleistungen umfassen. 

## Relevante Quellen zu OpenJDK-Versionen und Lizenzen

- [OpenJDK Projektseite](https://openjdk.org/)
- [Oracle OpenJDK](https://jdk.java.net/)
- [Eclipse Temurin (Adoptium)](https://adoptium.net/)
- [Amazon Corretto](https://aws.amazon.com/corretto/)
- [Azul Zulu](https://www.azul.com/downloads/)
- [BellSoft Liberica JDK](https://bell-sw.com/pages/liberica/)
- [Microsoft Build of OpenJDK](https://learn.microsoft.com/en-us/java/openjdk/)
- [Red Hat OpenJDK](https://developers.redhat.com/products/openjdk/overview)
- [SAP SapMachine](https://sap.github.io/SapMachine/)

## Lizenzpflicht

Bis einschließlich JDK 8u202 konnte das Oracle JDK unter der “Binary Code License” (BCL) kostenlos genutzt werden. Ab JDK 8u211 änderte Oracle die Lizenzbedingungen, sodass für kommerzielle Nutzung eine kostenpflichtige Lizenz erforderlich ist.  

Die Version JDK 8u202 entspricht Java SE Development Kit 8 Update 202.

Details zu JDK 8u202
- Versionsnummer: 1.8.0_202 aka Java SE 8 Update 202 (JDK 8u202)
- Veröffentlichungsdatum: 15. Januar 2019
- Lizenz: Oracle JDK 8u202 war die letzte Version, die unter der alten, kostenlosen Binary Code License (BCL) erhältlich war.
- Ab JDK 8u211 änderte Oracle die Lizenzbedingungen, sodass für kommerzielle Nutzung eine kostenpflichtige Lizenz erforderlich wurde.

**Support:**
- Oracle bietet keinen öffentlichen Support mehr für diese Version.
- OpenJDK 8u202 ist weiterhin unter GPLv2 mit Classpath-Ausnahme verfügbar.
- Alternative OpenJDK-Distributionen (z. B. Adoptium, Amazon Corretto, Azul Zulu) bieten weiterhin Support.

## JavaJDK durch OpenJDK ersetzen

### Unterschiede

- Java Flight Recorder und Mission Control (seit Java 11 Open Source, aber vorher proprietär)
- Grafik-Rendering & Fonts (unterschiedliche Implementierungen)
- Lizenzierte Verschlüsselungstechnologien

### ersetzen in Windows
- Lade das gewünschte OpenJDK von einer der oben genannten Seiten herunter.
- Entpacke die Datei nach C:\Program Files\Java\openjdk-17 (oder einen anderen Pfad deiner Wahl).
- Setze die Umgebungsvariablen:
    - Systemsteuerung → Erweiterte Systemeinstellungen → Umgebungsvariablen
    - Bearbeite JAVA_HOME und setze den Pfad auf C:\Program Files\Java\openjdk-17
    - Füge %JAVA_HOME%\bin zur Path-Variable hinzu


### Preise

am besten in tabellarischer form mit link zum shop

### Fehlervermeidung

falls Probleme im vorhinen bekannt sind, oder man gewisse Workarounds braucht um das system zu installieren, gehoert es hier hin. Links in die quellen

## Quellen / weitere ressourcen

Falls es quellen oder links zu updates gibt, hier rein  
