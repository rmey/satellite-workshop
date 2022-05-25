# 4. Deployment einer Anwendung auf OpenShift Satellite Cluster

{% hint style="info" %}
In dieser Übung lernen Sie, wie Sie eine Applikation in einem RedHat Openshift Cluster auf IBM Cloud Satellite zum Laufen bringen können.&#x20;
{% endhint %}



1. Öffnen Sie hierzu auf der linken oberen Seite das "IBM Cloud Menü". \
   ![](<.gitbook/assets/image (41) (1) (1).png>)
2. Navigieren Sie zu "Satellite" -> "Lokationen".\
   &#x20;![](<.gitbook/assets/image (45) (1) (1) (1).png>)
3. Dabei sollte eine Liste der verschiedenen IBM Cloud Satellite Lokationen erscheinen. Öffnen Sie mit einem Klick die "sat-lab-location"-Lokation.\
   ![](<.gitbook/assets/image (42) (1).png>)
4. Eine Übersicht zeigt die wichtigsten Informationen Ihrer IBM Cloud Satellite Lokation. Beispielsweise den Status, die Anzahl der zugewiesenen Hosts, den verwaltenden Standort (z.B. Dallas oder Frankfurt). Um eine detaillierte Ansicht der verschiedenen zugewiesenen Hosts zu überblicken, öffnen Sie auf der linken Seite den Menü-Punkt "Hosts".\
   ![](<.gitbook/assets/image (43) (1) (1).png>)&#x20;
5. Die dargestellte Liste zeigt alle Hosts, die der Lokation zugeordnet sind. Dabei sind weitere Informationen pro Hosts zu finden sowie die Zugehörigkeit. In der Übersicht sind die Hosts der Controlplane zuerst gelistet. Darauf folgend die Hosts, die einem Openshift-Cluster zugeordnet sind. Bitte beachten Sie, dass möglicherweise erst nach einer kurzen Ladezeit die Links (in blau gefärbt) zu den einzelnen Clustern erscheinen. Öffnen Sie mit einem Klick ihren zugeordneten Cluster. \
   ![](<.gitbook/assets/image (40) (1) (1).png>)\
   ![](<.gitbook/assets/image (47) (1) (1).png>)
6. Ein Dashboard des RedHat Openshift Clusters wird geöffnet. Dort sind wichtige Metriken zu Ihrem Cluster zu sehen, wie beispielsweise die Anzahl der Workernodes, die Clusterversion sowie Netzwerkbeschreibungen. Um nun tiefer in Ihr Cluster "einzusteigen" öffnen Sie die Openshift Webkonsole in dem Sie auf den blauen Button oben rechts klicken. Bitte beachten Sie, dass möglicherweise das Pop-Up Fenster blockiert wird und Sie es in Ihrem Browser freigeben müssen.\
   \
   &#x20;
7. Die Übersicht Ihres Clusters zeigt in der Openshift Konsole erneut alle wichtigen Informationen sowie Metriken.&#x20;

![](<.gitbook/assets/image (35).png>)

![](<.gitbook/assets/image (44) (1) (1).png>)

\
8\.  Da wir allerdings eine Applikation betreiben möchten, müssen Sie nun die Sicht in der Openshift Konsole wechseln. Klicken Sie hierzu links oben auf "Administrator". Eine Auswahl erscheint und öffnen Sie nun die "Developer"-Ansicht.&#x20;

![](<.gitbook/assets/image (41) (1).png>)\


9\. In der Developer-Sicht werden die verschiedenen Projekte dargestellt. Dabei ist bei Openshift jede Anwendung/Applikation einem Projekt zugeordnet. Für unsere Anwendung müssen wir nun ein neues Projekt erstellen. Klicken Sie hierzu auf "Create a project".  Alternativ können Sie unterhalb des Headers auf "Project" klicken. Eine Auflistung der verschiedenen Projekte erscheint und mit dem Button "Create project" können Sie ebenfalls ein neues Projekt anlegen. \
![](<.gitbook/assets/image (36) (1).png>)

10\. Geben Sie nun einen einzigartigen Namen für Ihr Projekt ein und klicken auf den Button "Create". \
![](<.gitbook/assets/image (46) (1).png>)

11\. Openshift bietet die Möglichkeit auf verschiedene Art und Weisen eine Applikation zu importieren bzw. zu deployen. In unserem Lab werden wir den Applikations-Code aus einem GitHub Repository ziehen und verwenden.\
\
12\. Das Github-Repository was für dieses Lab verwendet wird ist: \
\
[`https://github.com/frickD/openshift-nodejs`](https://github.com/frickD/openshift-nodejs)\
\
Dabei handelt es sich um eine einfache NodeJS Applikation mit einem Web-Frontend. Fügen Sie den Link des Repositories bei OpenShift ein. Openshift erkennt anhand des Codes, dass es sich um eine NodeJS Applikation handelt. Es sollte nun auch eine Vorschau erscheinen, welche NodeJS Version von Openshift verwendet wird, um die Applikation zu betreiben.\
\
![](<.gitbook/assets/image (40).png>)\


13\. Wenn Sie in der Übersicht weiter nach unten scrollen, können Sie zusätzlich den Namen der Applikation anpassen. Bitte vergeben sie einen eindeutigen Namen, z.B. durch anhängen eines Kürzels Ihres Namens.  Klicken Sie auf den "Create"-Button, um nun mit dem Deployen der Applikation zu beginnen.\
![](<.gitbook/assets/image (37) (1).png>)\
\
14\. Nun startet das automatische Deployment der Applikation. Es wird der Code aus dem Github Repository gezogen, ein Container erstellt und dieser Container im Openshift Cluster zum Laufen gebracht. Außerdem wird gleich eine Route für die Applikation erstellt. Sie können den Prozess beobachten in dem Sie auf das "NodeJS"-Logo in der Übersicht klicken. Bitte beachten Sie, dass dieser Prozess ein paar Minuten dauern könnte.\
![](<.gitbook/assets/image (47) (1).png>)\
\
![](<.gitbook/assets/image (45) (1).png>)

![](<.gitbook/assets/image (48) (1).png>)

15\. Wenn Die Anwendung fertig deployt ist kann diese in der Topology Sicht geöffnet werden. Sobald dies erfolgt ist, können Sie nun die Applikation in Ihrem Browser öffnen. Klicken Sie hierzu auf den "Link"-Button oder weiter unten auf den Link der Route.&#x20;

{% hint style="info" %}
Das Deployment ist abgeschlossen, sobald die Applikation in einem Pod läuft und der Status auf "Running" ist.\
![](<.gitbook/assets/image (39).png>)
{% endhint %}

\
![](<.gitbook/assets/image (38).png>)

16\. Herzlichen Glückwunsch! Sie haben Ihre erste Applikation in einem Openshift Cluster auf IBM Cloud Satellite zum Laufen gebracht! \
![](<.gitbook/assets/image (44) (1).png>)

