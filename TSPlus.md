---
title: TSPlus
description: 
published: true
date: 2025-03-11T10:50:39.135Z
tags: remote, rds
editor: markdown
dateCreated: 2025-03-11T08:57:27.703Z
---

# TSPlus - Remote Desktop Server

## Einleitung

Bei [TSPlus](https://terminalserviceplus.de) handelt es sich um ein deutsche Produkt was den Microsoft Remote Desktop ersetzt und somit auch keine Remote CALs benoetigt. TSPlus kann neben reinem RDP Hosting auch noch diverse verschiede Modi um Programme und Ordner exclusiv zu nutzen.

## Vorraussetzungen

Hostseitig: Ein Windows Server oder Windows 11 Pro. Bei Windows Server werden UserCALs benoetigt
Clientseitig: Ein RDP Client (OS unabhaengig) oder ein HTML5-faehiger Browser, fuer den Browser RDP

## Systemanforderungen

|number of users | Hardware |
| --- | --- |
| 3-5 | I5 or above One CPU 2 GHZ Minimum : 4 GB RAM Recommended : 8 GB RAM |
| 10 | I5 or above One CPU 2 GHZ Minimum : 8 GB RAM Recommended : 16 GB RAM |
| 25 | One CPU I7 or Xeon Minimum : 16 GB RAM Recommended : 32 GB RAM |
|50+ | 32 GB Dual CPU - SSD Disk dedicated to the system Minimum : 32 GB RAM Recommended : 64 GB RAM |

Each server (physical or virtual ones) can potentially handle up to 50 concurrent users. For over 50 concurrent sessions, we recommend using a farm of servers with the Load Balancing feature available in TSplus Remote Access Enterprise Edition.

## Installation

diese Informationen basieren auf der Version v18.20 vom 2025/03/25

- [Von der Webseite die aktuelle Installation herunterladen.](https://terminalserviceplus.de/download/)
- Installation starten und "erweiterte Installation waehlen"
- Wenn zusaetzlich die security Komponente installiert werden soll, nur das Setup heruntergeladen werden oder eine Proxy eingestellt werden muss, kann es in diesem Schritt getan werden.
![Installation Komponenten Auswahl](/bilder/TSPlus/installComponents.png "Komponenten Auswahl")
- Im naechsten Schritt koennen die Web Optionen angepasst werden.
![Installation Web Optionen](/bilder/TSPlus/installWebOptions.png "Web Optionen")
- Nach Abschluss der Installation muss der Server neu gestartet werden
![Abschluss der Installation](/bilder/TSPlus/installComplete.png "Installation Abgeschlossen")

## Konfiguration

diese Informationen basieren auf der Version v18.20 vom 2025/03/25

- Die Admin Konsole startet standardmaessig im Lite Modus. Der Lite Modus gibt zum start einen guten Ueberblick ueber die verschiedenen Funktionen. Ueber die Schaltflaeche rechts oben kann sie in den Expertenmodus versetzt werden.
![Lite Modus](/bilder/TSPlus/adminLite.png)

- Die Expertenansicht ist in die einzelnen Kategorien unterteilt
![Experten Ansicht](/bilder/TSPlus/adminExpert.png "Experten Ansicht" )

- Als erstes richten wir den Webzugriff mit dem Zertifikat ein. In der Expertenansicht unter Web und dann HTTPS.
![Web Einstellungen](/bilder/TSPlus/adminExpertWeb.png "Web Einstellungen")

- Unter HTTPS kann entweder ein bestehendes Zertifikat hinzugefuegt werden, oder ein neues bei Lets Encrypt beantragt werden. Fuer letzteres muss der Port80 fuer das Beantragen des Zertifikats durchgerooted sein.
![HTTPS Einstellungen](/bilder/TSPlus/adminExpertWebHTTPS.png "HTTPS Einstellungen")

- Um eine neues LE Zertifikat zu beantragen muessen folgende Vorrausetzungen erfuellt sein:
  - Sie müssen dieses Programm auf dem Gateway-Server oder einem eigenständigen Server und nicht auf einem Anwendungsserver
ausführen
  - Sie müssen denTSplus eigenen Webserver (HTTP auf Port 80) verwenden
  - Der Domänenname Ihres Servers muss über das öffentliche Internet erreichbar sein

- Sind diese Bedingungen erfuellt, kann ein LE Zertifikat angefragt werden. Dazu muss eine Administrator Adresse sowie die Public IP/Domain eingetragen sein.
![Lets Encrypt Zertifikat](/bilder/TSPlus/adminExpertWebHTTPSLEZert.png "Lets Encrypt Zertifikat")

- Ansonsten kann man auch ein eigenes Zertifikat hinzufuegen
![Eigenes Zertifikat](/bilder/TSPlus/adminExpertWebHTTPSEigenesZert.png "Eigenes Zertifikat")

- Unter Programme werden die verschiedenen Arten der Zugriffe eingestellt, siehe [genaue Beschreibung](#genaue-beschreibung)
- Um Shells und Standard Programm einfach auszuwählen, einfach per Doppelklick auf Microsoft Remote Desktop (1) die Auswahl der Gruppen/Nutzer öffnen (2). Hier können entweder alle Authentifizierten Benutzer aktiviert werden, oder einzelne User und Gruppen auswählen.

![Schnellauswahl](/bilder/TSPlus/adminExpertProgrammeAuswahl.png "Schnellauswahl")
- Als erstes Konfigurieren wir den Microsoft Remote Desktop Modus. Dazu zuerst Rechts auf Zuornung (User/App)(1).
![Programme](/bilder/TSPlus/adminExpertProgramme.png "Programme")

- Danach Auswahl Benutzer/Gruppen (1) die Auswahl öffnen. Benutzer oder Gruppe in lokalem Computer oder AD suchen (2). Gruppe/Nutzer über das AD Fenster (3) raussuchen und mit Benutzer oder Gruppe hinzufügen(4) auswählen
![User Auswahl](/bilder/TSPlus/adminExpertProgrammeUser.png "User Auswahl")

- sobald die Gruppe/Benutzer ausgewählt wurde, kann der Microsoft Remote Desktop ausgewählt werden (1) und mittels Veröffentlichen (2) bestätigt werden.
![Publish](/bilder/TSPlus/adminExpertProgrammePublish.png "Publish")

- über die Schnellauswahlmethode kann kontrolliert werden, welche Nutzer udn Gruppen hinzugefügt wurden

## allgemeine Informationen zur Software selbst

### Einsatzzweck der Software

TSPlus ist als guenstiger Ersatz fuer Windows RDP gedacht, da es Lifetime Lizenzen gibt. TSPlus kann mit jedem RDP Client oder HTML5-faehigen Browser (falls der webdienst verwendet wird) genutzt werden.

### genaue Beschreibung

TSPlus soll laut eigener Angabe nur Daten uebertragen, keine Bilder, was den Remote Datensparsamer und schneller machen soll. Auf meinem Testsystem konnte ich keinen Unterschied feststellen.

TSPlus bietet verschiedene remote Modi, um den Nutzerzugang einerseits zu erleichtern und andererseits eine Fehlnutzung des Systems zu verhindern:

- **Remote Desktop Client, vollstaendiger Zugriff auf den Desktop (Wie der Windows RDP)** TSplus Remote Access ist kompatibel mit jedem RDP Client von jedem Betriebssystem, also Windows, Linux, Android oder MAC OS. Somit kann ein sofortiger problemloser Remote Zugang zu einem TSplus Server erfolgen.
Weiterhin bietet TSplus einen eigenen mit umfangreichen Features versehenen 1-click Connection Client der über den im TSplus Remote Access enthaltenen Client Generator konfiguriert werden kann.
Zu beachten ist hierbei das nach der Generierung des TSplus RDP Client lediglich ein File mit den Parametern erzeugt wird und dieses dann einmalig mit dem Setup Connection Client Tool zur ausführbaren Datei compiliert wird.

- **Remote App Client** Mit dem Remote App Client können einzelne oder mehrere Anwendungen im Remote App Mode auf dem Desktop des Client PC dargestellt und ausgeführt werden. Der Client erhält dann nur den Zugriff auf seine Ihm zugewiesenen Programme, nicht aber auf den gesamten Desktop.
Für eine Applikation wird diese einfach dem entsprechenden User im TSplus Admin Tool zugewiesen. Für mehrere Applikationen gilt im Prinzip das Gleiche, allerdings erfolgt dann noch die Auswahl eines Containers in dem die Remote Anwendungen ähnlich eines Menüs angezeigt werden.

- **HTML5 Client** Über den im TSplus Remote Access integrierten Web-Server sind alle Anwendungen oder der Remote Desktop ebenfalls, völlig ohne zusätzlichen RDP Client, direkt über jeden Browser via HTML5 erreichbar. Somit kann jede publizierte Software webfähig Ihren Kunden oder Mitarbeitern bereit gestellt werden.
Erreichbar sind diese Applikationen von jedem beliebigen Endgerät, also Desktop, Tablet oder auch Smartphone völlig unabhängig von den auf Endgeräten eingesetzten Betriebssystemen. Die Anwendungen werden dann direkt in dem von User verwendetet Browser ausgeführt.
Es können eine oder mehrere Applikationen zur remote Nutzung zur Verfügung gestellt werden ohne das der User Zugang zum Desktop des System erhält. Die Programme können im Remote App Mode aufgerufen werden.

[unter diesem link gibt es eine Vorschau der verschiedenen modi mit kurzen Videos](https://terminalserviceplus.de/tsplus/remote-access-features/#rdesktop)

### Lizenzmodell

Die Lizenzen gehen nach Nutzerzahl und Umfang des Programmes. Im Standard ist es nur der RDP Client, HTML5 Browser Zugriff muss dazu gebucht werden. In der "rechts unten" Enterprise Edition ist fast alles enthalten fuer aktuell 1930EUR (Stand 11.03. 2025), nur die 2FA option muss fuer jeden Server einzeln zugebucht werden fuer 250EUR pro Server.
[hier sieht man das lizenzmodell](https://terminalserviceplus.de/preise/)

Auf die Frage ob wir MS RDS CALs benoetigen:

*Sie benötigen keinen MS Windows Terminalserver sondern nur einen normalen Windows Server (keine Essentials Edition) oder ein Windows Workstation OS (z.Bsp. W11 PRO).
Weiterhin benötigen Sie keine MS RDS CAL`s oder andere MS Lizenzen, außer bei einem Server OS natürlich die User CAL´s.*

### Preise

1930EUR fuer eine Enterprise Lizenz Stand 11. 03. 2025
[hier sieht man das lizenzmodell](https://terminalserviceplus.de/preise/)

### Fehlervermeidung

Wenn Sie ein Windows Server-Betriebssystem verwenden, stellen Sie sicher, dass die
Rollen TSE/RDS und TSE/RDS Lizenzen nicht installiert sind

## Quellen / weitere ressourcen

[offizielle Webseite](https://terminalserviceplus.de)
[offizieller Changelog](https://dl-files.com/TSplus-changelog.html)