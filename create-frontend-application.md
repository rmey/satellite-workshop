# 3. Arbeiten mit einer Satellite Lokation und Deployment eigener OpenShift Cluster



In der vorherigen Übungen haben wir eine neu Satellite Lokation erstellt, nun wollen wir mit einer existierenden Satellite Lokation arbeiten bzw. die Möglichkeiten kennenlernen diese zu verwalten und zeigen wie ein neuer OpenShift Cluster für IBM Cloud Satellite angelegt wird.

1. Im Cloud Menü öffnen wir die IBM Cloud Satellite Lokationen, es werden mehrere Lokationen angezeigt:\
   <img src=".gitbook/assets/image (50) (1).png" alt="" data-size="original">\

2. In der Liste öffnen wir durch Klick die sat-lab-location-new.\
   ![](<.gitbook/assets/image (50).png>)
3. In der Überblicksseite können wir verschieden Attribute der Satellite Lokation einsehen u. A.\
   \* Lokations ID\
   \* Management Region der IBM Cloud\
   \* Status der Lokation\
   \* Zonen\
   \* Infrastrukturinformationen\
   ![](<.gitbook/assets/image (43).png>)
4. Durch Klick auf Menü Hosts können wir die zugeordneten Hosts der Lokation und deren Zustand sehen, sowie den Lebenszyklus der Maschinen managen.\
   ![](<.gitbook/assets/image (46).png>)\
   ![](<.gitbook/assets/image (39).png>)\


{% hint style="info" %}
Hosts können verschiedene Funktionen innerhalb einer Satellite Lokation haben. Für die Satellite Control Plane werden ein mindestens 3 bzw. Vielfaches von 3 benötigt um grundlegende Satellite Funktionen zu ermöglichen. Die Control Plane ist quasi die lokale Steuerzentrale einer Lokation und beinhaltet z. B. die Satellite Link Services oder die Master von OpenShift Clustern. Die Control Plane sollte hochverfügbar auf mehrere Racks/Zonen je nach Provider aufgeteilt werden. Die Controlplane nutzt Hypershift um mehrere Master in den Control Plane Host zu managen. In unserem Beispiel mit 6 Maschinen mit jeweils 4vCPU/16GB RAM in der Controlplane können wir\
bis zu 5 clusters mit je 20 Workernodes oder 80 worker über 2 Clusterverwalten. Jeder Cluster hat in der Controlplane mehrere Master, so das beim Ausfall einer Zone, es zu keinen Ausfall der Services kommt. &#x20;

\
Hosts können neben der Control Plane auch Satellite enabled Service Instanzen zugeteilt werden, so z. B.\
\* OpenShift Clustern\
\* Datenbankservices PostgreSQL, etcd, Redis, RabbitMQ, MySQL...\
\* Keyprotect\
\* Eventstream (Kafka as a Service)\
Zu einer Lokation können jederzeit neue Hosts hinzugefügt werden oder alte Hosts entfernt werden.
{% endhint %}

5\. In der Service View können wir die Satellite enabled Service Instanzen sehen, in unserem Beispiel haben wir 3 OpenShift Cluster in der Lokation.\
![](<.gitbook/assets/image (48).png>)

6\. Unter Link Endpoints können wir die Endpunkte der Satellite Lokation on-prem und in der IBM Cloud Control Region verwalten. Ebenfalls können Monitoring Dashboard aufgerufen werden, um die Verbindungen und Zugriffe zu überwachen bzw. zu protokollieren.\
![](<.gitbook/assets/image (47).png>)\
7\. Im folgenden Schritt wollen wir sehen wie ein neuer Cluster mit Satellite konfiguriert wird. Das anlegen eines neuen Clusters kann nicht parallel für alle Teilnehmer verlaufen, nur sequentiell, weshalb wir diesen Schritt nur illustrieren (der Cluster wäre ungefähr nach 15 min provisioniert):\
Wir navigieren zu dem Cluster Menu von IBM Cloud Satellite:\
![](<.gitbook/assets/image (42).png>)\


8\. In der Liste sehen wir wieder die existierenden Cluster. Dort klicken wir auf Create Cluster:

![](<.gitbook/assets/image (37).png>)

9\. Der Dialog für das anlegen eines Clusters erscheint, und wir können nun auswählen, ob wir den OpenShift Cluster in der IBM Cloud (VPC oder Classics Network) oder in einer Satellite Lokation anlegen wollen. Wir wollen die Konfiguration für einen Satellite Cluster durchführen.\
![](<.gitbook/assets/image (38).png>)\
\
10\. Dazu wählen wir unsere Lokation und den Typ der Worker Nodes aus, welche dann aus der Liste der verfügbaren Hosts der Lokation zugwiesen werden sollen.\
![](<.gitbook/assets/image (36).png>)\
\
11\. Wir können weitere Parameter festlegen, z. B.

* Subscription Pull Secret für Bring Your Own Subscription für OpenShift Lizenz
* zentrale Konfiguration des Clusters zulassen über Satellite Config
* Clusternamen

![](<.gitbook/assets/image (39) (1).png>)

12\. Das Anlegen des Clusters wird nicht durchgeführt sondern für alle Teilnehmer separat gezeigt.











&#x20;\
\
\
\
\
\
\
\
\
\
