# MetaCompliance

## Einleitung

MetaCompliance bietet umfassende Lösungen für Cybersecurity-Schulungen und Compliance-Management an. Ihre Produkte umfassen Phishing-Simulationssoftware, Datenschutzmanagement-Tools, personalisierte Security-Awareness-Trainings und Policy-Management-Software. Diese Werkzeuge helfen Unternehmen, ihre Mitarbeiter effektiv zu schulen, Sicherheitsrichtlinien zu verwalten und auf Vorfälle angemessen zu reagieren.

## Funktionsumfang

### Automatisierung der Security Awareness

Planen Sie Ihre jährliche Awareness-Kampagne mit ein paar Klicks

### Phishing-Simulation

Stoppen Sie auf der Stelle Phishing-Angriffe dank preisgekrönter Phishing-Software

### E-Learning Cyber Security

E-Learning zur Cyber Security: Entdecken Sie unsere preisgekrönte E-Learning-Bibliothek, maßgeschneidert für jede Abteilung

### Cyber Police

Schulung zur Cyber Security für Abteilungen

### Policy Management

Zentralisieren Sie Ihre Richtlinien an einem Ort und verwalten Sie mühelos die Lebenszyklen von Richtlinien

### Datenschutzmanagement

Einfache Kontrolle, Überwachung und Verwaltung der Compliance

### Incident Management

Übernehmen Sie die Kontrolle über interne Vorfälle und beseitigen Sie die wichtigsten Probleme

## Policies

### Erstellung

- Auf der linken Seite den reiter Policy aufklappen und mittels Policy creation eine neue erstellen
![Startseite](/bilder/MetaCompliance/policy.png "Startseite")

- Im ersten Tab werden die allgemeinen Infos sowie der Inhalt der policy eingetragen 
  - Name erscheint in der Uebersicht der Policies. Hier sollte man eine Namenskonvention einfuehren
  - Titel ist der Titel den der Policy Empfaenger sieht
  - Ueber Keywords koennen Tags gesetzt werden (ich habe noch keine Verwendung der Tags gesehen)
  - Der Policy Author wird dem Nutzer der die Policy empfaengt nicht angezeigt. Dieser ist wohl nur in der Policy Uebersicht fuer Administratoren zu sehen.
  - Die Customer Policy Version wird in der Policy Uebersicht des Nutzers angezeigt. Sollte also sinnvoll ausgefuellt werden
  - In den Sektionen koennen 3 unterschiedliche typen festgelegt werden, die sich in der Darstellung der Policy unterscheiden
    - Alle 3 Typen der sektionen haben einen Titel und eine Description, wobei zweiteres dem User nicht angezeigt wird
    - In der PDF Sektion kann ein PDF hochgeladen werden. dieses wird dann direkt angezeigt
    - Bei Custom Text kann mittels einem WYSIWYG Editor oder HTML ein Text frei generiert und angezeigt werden
    - Mit Linked URL wird einfach nur ein Link dargestellt
![Policy erstellen](/bilder/MetaCompliance/policyPolicy.png "Policy erstellen")

- Beispielbild PDF Section
![PDF Section](/bilder/MetaCompliance/policyPolicySectionPDF.png "PDF Section")

- Beispielbild Custom Text Section
![Custom Text Section](/bilder/MetaCompliance/policyPolicySectionCustomText.png "Custom Text Section")

- Beispielbild PDF Section
![URL Section](/bilder/MetaCompliance/policyPolicySectionURL.png "URL Section")

- Unter dem Tab Response Options koennen die Antwortmoeglichkeiten erstellt werden. Man hat die Wahl aus 2 Typen
![Response Options](/bilder/MetaCompliance/policyPolicyResponseOptions.png "Response Options")
  - Close Message ist eine Simple Antwort mit der die Policy versehen werden kann. Bspw einfach Annehmen oder Ablehnen.
  - Mit der Antwort Request Exemption kann der Policy Empfaenger in einem Freitextfeld mitteilen, warum er glaubt das er nicht von dieser Policy betroffen ist oder man von ihr ausgenommen werden sollte
  ![Response Options](/bilder/MetaCompliance/policyPolicyResponseOptionsExemption.png "Response Options")


## Quellen / weitere ressourcen

Falls es quellen oder links zu updates gibt, hier rein  

If you have enabled "Create/Add Sub-group(s)" your groups will be created based on the Department and GroupName values you provide in your spreadsheet. The Department value you use corresponds to Parent User Groups and the GroupName value corresponds to Sub Groups. A Parent User Group can either contain a flat list of users, or a list of Sub Groups that each contain users. A Parent Group cannot contain both users and Sub Groups at the same level so it is important that you ensure your spreadsheet is set up correctly otherwise users may not be added to groups based on the existing structure.
See the example below:

All users belonging to “Australia” and “Europe” will be added to groups correctly, however, not all users from “North America” will be added to groups as some users have been provided with a Department and GroupName and another provided with Department only. As per the example, having users and Sub Groups at the same level is not allowed – in this case, a group called “North America” with a Sub Group of “New York” will be created and 3 users assigned correctly, however Cindy Smith will not be added to a group as “North America” contains Sub Groups and Cindy has not been provided with a GroupName value.


File Preparation Guidelines: File must be uploaded as a CSV file or Excel file. Your file must contain all the field headings (shown in bold) in the order shown below. All fields must be populated with data with the exemption of 'GroupName', 'SupervisorEmail' and 'SupervisorsManagerEmail'.
 A Supervisor or Supervisor Manager can only be successfully added if their email account is not disabled and exists on the system within this company. You can only add a Supervisors' Manager if you also provide a Supervisor.

 forename
 surname
 email
 department
UserPrincipalName 

 Forename 
 Surname 
 Email
UserPrincipalName 
Department 
Domain
GroupName