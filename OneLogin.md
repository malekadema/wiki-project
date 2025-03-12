# OneLogin

## Einleitung

onelogin ist ein tool um mittels eines Accounts sich bei verschiedenen Diensten zu authentifizieren. Dabei werden die Credentials der einzelnen Seiten an den Account geknuepft. OneLogin kann sich die Userdaten aus dem AD holen. Ausserdem kann ueber die Software gesteuert werden, wer welche App verbindungen nutzen darf.

## Vorraussetzungen

geoeffnete Ports zu den Europaeischen servern unter: 52.29.255.192/26, 52.48.63.0/26, 18.130.91.64/29, 23.183.112.0/24, 23.183.113.0/24
Onelogin kommuniziert ueber Port 8080 mit dem AD, wenn es mehrere ADs sind muss man Port 443 nehmen.
[Liste der Server, IP Adressen und Ports](https://onelogin.service-now.com/support?id=kb_article&sys_id=67fc44dc97894e10c90c3b0e6253af24&kb_category=a0b5e130db185340d5505eea4b961957#ips)
[Artikel aus dem Support von OneLogin](https://support.onelogin.com/kb/4266967/onelogin-domains-and-ip-addresses)

es muss ein Domain Service Account erstellt werden mit Zugriff auf die Domain, es muss aber kein dedizierter AD Admin sein.
[Artikel aus dem Support von OneLogin](https://onelogin.service-now.com/support?id=kb_article&sys_id=ed0f975d87e80a10c44486e5cebb35e1&kb_category=ff57e170db185340d5505eea4b961929)

## Hauptteil

### Vorbereitung

unter OneLogin.com wird die Subdomain fuer den Einloggvorgang eingerichtet. [Zum Beispiel die Testumgebung](https://werbas-ksr-test.onelogin.com)

auf dem/den ADC Server(n) muessen die entsprechenden Ports (siehe Vorraussetzungen) geoeffnet sein.

Optional kann der Domain Service Account vorher stellt werden, dies geht aber auch im Installationsprozesses des ADConnectors.

### Installationsanleitung

### Verbindung OL zu AD

[Originalanleitung im Support von OL](https://support.onelogin.com/kb/4250579/install-configure-active-directory-connector-5)

- Im OL Portal anmelden und rechts oben auf Administration
- unter "Users"-> "Directories" kann ein neuer Actice Directory Connector hinzugefuegt werden
- Der Assistent oeffnet sich, unter A) kann ein Name fuer den Connector vergeben werden
- Unter B) kann die aktuellste Connector Software fuer den AD Server heruntergeladen werden
- Unter C) muss der Token kopiert werden
- Den installationsassistenten fuer den Connector starten
- den Token eingeben
- den Domain Service Account entweder auswaehlen (wenn er vorher schon erstellt wurde) oder einen neuen erstellen
- Port eintragen. Wenn es nur ein einzelnder AD-Server ist, kann 8080 verwendet werden, ansonsten muss 443 genutzt werden
- Am Schluss die checkbox auswaehlen um die zu Sychronisierenden UOs auszuwaehlen
- im Online Portal sollte die Domain Verbindung schon sichtbar sein

Damit User gesyncht werden, muessen mindestens folgende Felder in ihrem User Profil ausgefuellt sein:

- given name (first name)
- sn (sur name)
- mail
- distinguishedName
- userPrincipalName
- sAMAccountName
- memberOf
- status

### Fehlervermeidung

Der ADConnector gibt keine sichtbaren fehlermeldungen raus. ich musste zuerst einiges ausprobieren um dann festzustellen, dass wohl die ports allein nicht reichen, sondern alle IP Adressen in den firewall regeln eingetragen sein muessen, um dort eine Konnektivitaet herstellen zu koennen. Bei einem Produktivsystem wuerde ich auf jeden fall die regeln deutlich enger gestalten und auch ueberfluessiges nach dem sync wieder deaktivieren/blocken.

## Quellen / weitere ressourcen

Falls es quellen oder links zu updates gibt, hier rein
