# 2. Anlegen eines IBM Cloud Satellite Standorts

{% hint style="info" %}
Im Rahmen dieses Labs wird ein IBM Cloud Satellite Standort (sog. Location/Lokation) erstellt. Ein IBM Cloud Satellite Standort ist ein Ort ausserhalb eines IBM Cloud Rechenzentrums, z.B. ein kundeneigenes Rechenzentrum. Diese Satelliten-Lokation kann dann genutzt werden um dort IBM Cloud Services auszurollen (z.B. voll verwaltetes Red Hat OpenShift), nachdem die Lokation erstellt und konfiguriert ist... und genau das ist der Gegenstand dieses Labs.
{% endhint %}

1. In der IBM Cloud Console im Navigationsmenü ("Hamburger"-Menü) den Eintrag "Satellite" > "Overview/Übersicht" auswählen
2. ![](<.gitbook/assets/image (40) (1).png>)
3. ![](<.gitbook/assets/image (36) (1).png>)

{% hint style="info" %}
Die Satellite-Übersichtsseite enthält viele gute Links, Videos und Hintergrundinformationen rund um IBM Cloud Satellite.
{% endhint %}

4\. Auf der Satellite Übersichtsseite den Menüeintrag "Locations/Standorte" auswählen. Die Standortseite gibt einen Überblick über alle bereits angelegten Standorte

5\. Für diesen Workshop ist bereits (mindestens) ein Standort "sat-lab-location" vorkonfiguriert. Diesen Standort werden wir in einem späteren Lab benutzen.  Neben dem Lokationsnamen sind in der Standortseite wichtige weitere Informationen bzgl. eines Standorts aufgeführt (Zustand der Lokation, IBM Cloud RZ über das der Standort betankt und verwaltet wird, Ressourcengruppe, Anzahl der in der Lokation verfügbaren Hosts  und Erstellungsdatum).

![](<.gitbook/assets/image (38) (1).png>)

6\. Auf der Standorte-Seite den (blauen) "Create location/Standort erstellen" Button drücken. Auf der Vorlagenseite finden sich einige vordefinierte Templates für unterschiedliche Standort-Zielinfrastrukturen, z.B. gängige Hyperscaler (AWS, Azure, GCP).

![](<.gitbook/assets/image (39) (1).png>)

7\. Durch Selektieren des "Edit/Bearbeiten"-Eintrags gelangt man auf die Konfigurationsseite. Dort entsprechend folgende Attributwerte anpassen Name: sat-loc-\<Benutzerkennung oder -name> Managed from/Verwaltet über: Frankfurt (Hier sollte immer das am geografisch nächsten am Satellite-Standort (z.B. eigenes RZ) liegende IBM Rechenzentrum  ausgewählt werden)

![](<.gitbook/assets/image (35).png>)

8\. Durch Drücken des (blauen) "Create location/Standort erstellen" Buttons, wird die Lokation erzeugt. Nach kurzer Zeit wird im Browser automatisch auf die Satellite Lokationserstellungs-Seite weitergeleitet

![](<.gitbook/assets/image (37).png>)

{% hint style="info" %}
Der Standort selber ist fertig konfiguriert, der grüne Fortschrittsbalken "Creation in progress.../Die Erstellung wird ausgeführt..." gibt erst auf, wenn dem Standort auch Hosts/Server zugeordnet werden.  Diesen Vorgang wollen wir uns nun in der Theorie anschauen (aus Zeitgründen können wir ihn im Rahmen des Labs nich praktisch durchführen).
{% endhint %}

9\. Durch Selektieren des (blauen) "Next/Weiter"-Buttons gelangt man auf die "Attach Hosts.../Hosts an Ihren Standort anhängen..."-Seite

10\. Dort kann durch Drücken des (blauen) "Generate Script/Script genieren"-Buttons ein  Script erzeugt werden.

![](<.gitbook/assets/image (38).png>)

11\. Im Popup-Screen "Generate Script/Script genieren" kann das generierte Script entsprechend durch Drücken des (blauen) "Download script/Script herunterladen"-Buttons auf den lokalen PC heruntergeladen werden

{% hint style="info" %}
Mit einem Editor kann das Script entsprechend inspiziert werden, es ist ein normales Unix/Linux-Shell-Script. Dieses Shell-Script muss nun auf allen Hosts/Servern, die zu dieser Lokation gehören sollen ausgeführt werden, um diese dem Standort zuzuordnen. In der Praxis wird dieses Script in das entsprechende Provisionierungsverfahren der Hosts/Server eingebunden (z.B. Ansible, VMware-Templates, etc).
{% endhint %}
