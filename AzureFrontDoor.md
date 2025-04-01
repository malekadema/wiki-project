# Azure Front Door

## Einleitung

Azure Front Door bietet ein schnelles, zuverlässiges und sichereres, modernes Cloud-CDN (Content Delivery Network) unter Verwendung des globale Microsoft-Umkreisnetzwerks für die Integration von intelligentem Bedrohungsschutz. Azure Front Door befindet sich am Umkreisnetzwerkstandort und verwaltet Benutzeranforderungen an Ihre gehosteten Anwendungen. Benutzer*innen stellen über das globale Microsoft-Netzwerk eine Verbindung mit Ihrer Anwendung her. Azure Front Door leitet die Benutzeranforderungen dann an das schnellste Anwendungs-Back-End mit der größten Verfügbarkeit weiter.

## Vorraussetzungen

hier gehoeren Systemvorraussetzungen hard- sowie software hin

## Hauptteil

### Optimieren der Inhaltsübermittlung durch Azure Front Door

Azure Front Door verwendet das anycast-Protokoll mit geteiltem TCP auf Schicht 7, um HTTP/S-Clientanforderungen an das schnellste Anwendungs-Back-End mit der größten Verfügbarkeit weiterzuleiten. Die Art und Weise, wie Azure Front Door Anforderungen weiterleitet, hängt von der ausgewählten Routingmethode und der Back-End-Integrität ab. Azure Front Door unterstützt vier Routingmethoden, wie in der folgenden Tabelle beschrieben:

| Routingmethode | BESCHREIBUNG |
| --- | --- |
| Latency | Hilft sicherzustellen, dass Anforderungen an diejenigen Back-Ends gesendet werden, die innerhalb eines akzeptablen Empfindlichkeitsbereichs die niedrigste Latenz aufweisen. |
| Priority | Verwendet vom Administrator an Ihre Back-Ends zugewiesene Prioritäten, wenn Sie ein primäres Back-End zur Verarbeitung des gesamten Datenverkehrs konfigurieren möchten. |
| Gewichtet | Verwendet vom Administrator an Ihre Back-Ends zugewiesene Gewichtungen, wenn Sie Datenverkehr über eine Sammlung von Back-Ends verteilen möchten. |
| Sitzungsaffinität | Ermöglicht ihnen das Konfigurieren der Sitzungsaffinität für Ihre Front-End-Hosts oder -Domänen. Dadurch wird sichergestellt, dass Anforderungen desselben Endbenutzers an dasselbe Back-End gesendet werden. |


### Features

Azure Front Door stellt die folgenden wichtigsten CDN-Features zur Verfügung:
- Beschleunigung dynamischer Websites
- CDN-Cacheregeln
- Unterstützung benutzerdefinierter HTTPS-Domänen
- Azure-Diagnoseprotokolle
- Dateikomprimierung
- Geofilterung

### Software Firewall 

Die Azure Front Door-Webanwendungsfirewall basiert auf Richtlinien, die Sie einer oder mehrere Instanzen von Azure Front Door zuordnen können. Diese Firewallrichtlinien bestehen aus:
- Verwalteten Regelsätzen, einer Sammlung von vorkonfigurierten Regeln.
- Benutzerdefinierten Regeln, die Sie konfigurieren können.

#### Firewall Regeln

Eine Regel besteht aus:
- Einer Bedingung, die bestimmt, ob eine Regel für den jeweiligen Datenverkehr gilt.
- Eine Priorität, die, basierend auf der Wichtigkeit, die Reihenfolge bestimmt, in der eine Regel verarbeitet wird.
- Einer Aktion: Kann Zulassen, Blockieren Protokollieren oder Umleiten sein.
- Einem Modus. Es gibt zwei Modi:
    - Erkennung: In diesem Modus nimmt Azure Web Application Firewall nur Überwachung und Protokollierung vor. Es wird keine andere Aktion ausgeführt.
    - Prävention: In diesem Modus führt Azure Web Application Firewall die definierte Aktion aus.

### Produkte mit geringerem Funktionsumfang für speziellere Lösungen

- Azure Traffic Manager, der DNS-basiertes globales Routing bereitstellt. Er bietet jedoch keine TLS-Protokollbeendigung (Transport Layer Security), SSL-Auslagerung, pro HTTP/HTTPS-Anforderung oder Verarbeitung auf Anwendungsebene.
- Azure Application Gateway, das einen Lastenausgleich zwischen Ihren Servern in einer Region auf Anwendungsebene durchführen kann.

### Lizenzmodell

- lizenzen gebunden
- jaehrliche lizenzen oder lifetime
- koennen sie uebertragen werden

### Preise

Preise

In Azure Front Door wird nach ausgehenden Datenübertragungen, eingehenden Datenübertragungen und Routingregeln abgerechnet. Wenn Sie Azure Web Application Firewall und Azure Content Delivery Network implementieren, ist Folgendes im Preis enthalten:
- Eine monatliche Gebühr pro Richtlinie.
- Weitere Gebühren für benutzerdefinierte Regeln und verwaltete Regelsätze.

Die Abrechnung für Azure Front Door Standard/Premium basiert auf den folgenden Kriterien:
- Auf Stundenbasis berechnete feste Gebühr
- Ausgehende Datenübertragungen
- Eingehende Datenübertragungen
- Vom Client eingehende Anforderungen an Azure Front Door-POPs (Point-of-Presence).


### Fehlervermeidung

falls Probleme im vorhinen bekannt sind, oder man gewisse Workarounds braucht um das system zu installieren, gehoert es hier hin. Links in die quellen

## Quellen / weitere ressourcen

Falls es quellen oder links zu updates gibt, hier rein  
