# 4. Deployment einer Anwendung auf OpenShift Satellite Cluster

{% hint style="info" %}
In dieser Übung lernen Sie, wie Sie eine Applikation in einem RedHat Openshift Cluster auf IBM Cloud Satellite zum Laufen bringen können.&#x20;
{% endhint %}



1. Öffnen Sie hierzu auf der linken oberen Seite das "IBM Cloud Menü". \
   ![](<.gitbook/assets/image (41) (1).png>)
2. Navigieren Sie zu "Satellite" -> "Lokationen".\
   &#x20;![](<.gitbook/assets/image (45) (1).png>)
3. Dabei sollte eine Liste der verschiedenen IBM Cloud Satellite Lokationen erscheinen. Öffnen Sie mit einem Klick die "sat-lab-location"-Lokation.\
   ![](<.gitbook/assets/image (42).png>)
4. Eine Übersicht zeigt die wichtigsten Informationen Ihrer IBM Cloud Satellite Lokation. Beispielsweise den Status, die Anzahl der zugewiesenen Hosts, den verwaltenden Standort (z.B. Dallas oder Frankfurt). Um eine detaillierte Ansicht der verschiedenen zugewiesenen Hosts zu überblicken, öffnen Sie auf der linken Seite den Menü-Punkt "Hosts".\
   ![](<.gitbook/assets/image (43) (1).png>)&#x20;
5. Die dargestellte Liste zeigt alle Hosts, die der Lokation zugeordnet sind. Dabei sind weitere Informationen pro Hosts zu finden sowie die Zugehörigkeit. In der Übersicht sind die Hosts der Controlplane zuerst gelistet. Darauf folgend die Hosts, die einem Openshift-Cluster zugeordnet sind. Bitte beachten Sie, dass möglicherweise erst nach einer kurzen Ladezeit die Links (in blau gefärbt) zu den einzelnen Clustern erscheinen. Öffnen Sie mit einem Klick ihren zugeordneten Cluster. \
   ![](<.gitbook/assets/image (40) (1).png>)\
   ![](<.gitbook/assets/image (47).png>)
6. Ein Dashboard des RedHat Openshift Clusters wird geöffnet. Dort sind wichtige Metriken zu Ihrem Cluster zu sehen, wie beispielsweise die Anzahl der Workernodes, die Clusterversion sowie Netzwerkbeschreibungen. Um nun tiefer in Ihr Cluster "einzusteigen" öffnen Sie die Openshift Webkonsole in dem Sie auf den blauen Button oben rechts klicken. Bitte beachten Sie, dass möglicherweise das Pop-Up Fenster blockiert wird und Sie es in Ihrem Browser freigeben müssen.\
   \
   &#x20;
7. Die Übersicht Ihres Clusters zeigt in der Openshift Konsole erneut alle wichtigen Informationen sowie Metriken.&#x20;

![](<.gitbook/assets/image (35).png>)

![](<.gitbook/assets/image (44).png>)

\
8\.  Da wir allerdings eine Applikation betreiben möchten, müssen Sie nun die Sicht in der Openshift Konsole wechseln. Klicken Sie hierzu links oben auf "Administrator". Eine Auswahl erscheint und öffnen Sie nun die "Developer"-Ansicht.&#x20;

![](<.gitbook/assets/image (41).png>)\


9\.&#x20;

