# Raidboxes

## Einleitung

Raidboxes ist ein Anbieter fuer WordPress Installationen in Containern. So koennen unabhaengig voneinander einzelne WordPress installationen einfach erstellt, uebertragen und verwaltet werden.

## Uebertragung einer bestehenden WordPress Installation zu einer neuen RaidBox

### Vorbereitung

#### RaidBoxes

- neue RaidBox anlegen
- Namen passend zur Webseite vergeben
- richtige WordPress Version auswaehlen. (Notfalls Quellsystem updaten)
- passende PHP Version auswaehlen (nach erstellung der Box einstellbar)
- passendes Wordpress Datenbank Prefix eintragen
- Administrator Account Daten notieren (ist der WPAministrator Account)

#### bestehende Installation

- PHP Version ermitteln
  - Im Wordpress Backend > Werkzeuge > Website-Zustand
  - Tab Bericht
  - Abschnitt Server
  - PHP-Version
- WP Prefix ermitteln
  - [Query Monitor Plugin](https://wordpress.org/plugins/query-monitor/) installieren und aktivieren
  - Im Wordpress Backend erscheint oben in der Admin-Bar der neue Eintrag Query Monitor
  - Klicken und auf Database Queries
  - in der SQL Abfrage sieht man die verwendeten Tabellen, beispielsweise wp_posts, wp_options
  - Der Teil vor und mitsamt dem Unterstrich ist das Prefix. Beispielsweise wp5_
- [Migrate Guru Plugin](https://wordpress.org/plugins/migrate-guru/) Installieren und aktivieren
- Migrate Guru Plugin aufrufen, email Adresse des Raidbox accounts eintragen
- 

### Installationsanleitung

schritt fuer schrittanleitung, am besten mit bildern, fuer den installationsprozess

- schritt 1
- schritt 2
- schritt 3

### Fehlervermeidung

falls Probleme im vorhinen bekannt sind, oder man gewisse Workarounds braucht um das system zu installieren, gehoert es hier hin. Links in die quellen

## Quellen / weitere ressourcen

[Anleitung zum Umzug bei Raidboxes](https://helpcenter.raidboxes.de/de/articles/4394042-wordpress-umzug-mit-migrate-guru)

beim umzug werden die tabellen angezeigt. habe einen screenshot gemacht 16. april 2025 11:14Uhr 