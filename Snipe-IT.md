# Snipte-IT

## Einleitung

[Snipe-IT](https://snipeitapp.com) ist ein Open Source Lösung für Asset- und Lizenzverwaltung.

## Vorraussetzungen

In unserem Fall hosten wir es selbst, deshalb über einen Docker Container.
Für ein Lizenzfreies hosten (Lizenz: Open Source (Apache 2.0)) nutze ich aktuell [Rancher Desktop](https://rancherdesktop.io). Rancher Desktop kann nach aktuellem Stand (5.5. 2025) noch nicht wie Docker Dekstop Docker Instanzen mit mehreren Containern über die UI runterladen und zur Verfügung stellen. aber man kann mit dem Local Cluster die gestarteten Deployments überwachen 

## Hauptteil

### Vorbereitung

- WSL2 installieren (wsl --install)
- Linux Distribution installieren (bspw Ubuntu wsl --install -d Ubuntu)
- [Rancher Desktop](https://rancherdesktop.io) installieren

### Installationsanleitung

#### Offizielle Anleitung

Über die [offizielle Anleitung von Snipe-IT](https://snipe-it.readme.io/docs/docker)

#### Mittels yaml Datei

- Für Snipe-IT werden zwei ccontainer benötigt, einer für die Snipe-IT App sowie einer für die SQL Datenbank. Beides kann über ein .env bzw .yaml file erledigt werden. Weiter unten ein Beispiel für eine fertige yaml Datei.
- Es wird ein App Key benötigt. Entweder erstellt man vorher einen neuen mittels `kubectl compose run --rm app php artisan key:generate --show` 
- oder man lässt das deployment einmal laufen und sucht erst mittels `kubectl get pods` die containerID heraus und schaut dann mittels `kubectl logs snipeit-<containerID>` den Fehler an. Dort wird ein App Key vorgeschlagen den man übernehmen kann
- Im service von SnipeIT kann der Port für die Node festgelegt werden. Dieser Port muss im deployment bei APP_URL mit eingetragen werden

[Beispiel für ein Docker-Deployment yaml](/files/beispielDeployment.yaml)


    ---
    apiVersion: v1
    kind: PersistentVolumeClaim
    metadata:
      name: mysql-pvc
    spec:
      accessModes:
        - ReadWriteOnce
      resources:
        requests:
          storage: 1Gi
    ---
    apiVersion: apps/v1
    kind: Deployment
    metadata:
      name: mysql
    spec:
      replicas: 1
      selector:
        matchLabels:
          app: mysql
      template:
        metadata:
          labels:
            app: mysql
        spec:
          containers:
            - name: mysql
              image: mysql:5.7
              env:
                - name: MYSQL_DATABASE
                  value: snipeit
                - name: MYSQL_ROOT_PASSWORD
                  value: rootpass
                - name: MYSQL_USER
                  value: snipeit
                - name: MYSQL_PASSWORD
                  value: snipepass
              ports:
                - containerPort: 3306
              volumeMounts:
                - mountPath: /var/lib/mysql
                  name: mysql-storage
          volumes:
            - name: mysql-storage
              persistentVolumeClaim:
                claimName: mysql-pvc
    ---
    apiVersion: v1
    kind: Service
    metadata:
      name: mysql
    spec:
      ports:
        - port: 3306
      selector:
        app: mysql
    ---
    apiVersion: apps/v1
    kind: Deployment
    metadata:
      name: snipeit
    spec:
      replicas: 1
      selector:
        matchLabels:
          app: snipeit
      template:
        metadata:
          labels:
            app: snipeit
        spec:
          containers:
            - name: snipeit
              image: snipe/snipe-it
              ports:
                - containerPort: 80
              env:
                - name: APP_URL
                  value: http://localhost:30080
                - name: APP_KEY
                  value: "base64:Gx9z3A0Ht4v9sYq9K4t1aB4k6NHlT0ZpXKk3J6cYdG8="
                - name: DB_HOST
                  value: mysql
                - name: DB_DATABASE
                  value: snipeit
                - name: DB_USERNAME
                  value: snipeit
                - name: DB_PASSWORD
                  value: snipepass
                - name: DB_PORT
                  value: "3306"
    ---
    apiVersion: v1
    kind: Service
    metadata:
      name: snipeit-service
    spec:
      type: NodePort
      selector:
        app: snipeit
      ports:
        - protocol: TCP
          port: 80
          targetPort: 80
          nodePort: 30080

- mittels `kubectl apply -f beispielDeployment.yaml` wird die Beispiel Konfiguration deployed
- sobald das deployment durchgelaufen ist, kann mittels `kubectl get pods` kontrolliert werden, dass beide CContainer laufen. sie sollten als running angezeigt werden
- über `kubectl get svc` sieht man die laufenden Dienste. dort sollte der SnipeITservice auf der en

schritt fuer schrittanleitung, am besten mit bildern, fuer den installationsprozess

- schritt 1
- schritt 2
- schritt 3

### Fehlervermeidung

falls Probleme im vorhinen bekannt sind, oder man gewisse Workarounds braucht um das system zu installieren, gehoert es hier hin. Links in die quellen

## Quellen / weitere ressourcen

Falls es quellen oder links zu updates gibt, hier rein
