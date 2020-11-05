---
lab:
    title: 'Lab 4: Erstellen einer modellgesteuerten App'
    module: 'Modul 3: Erste Schritte mit Power Apps'
---

# Modul 3: Erste Schritte mit Power Apps
## Lab 3: Erstellen einer modellgesteuerten App

Szenario
========

Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus. Campusbesucher werden derzeit auf Papier erfasst. Die Informationen werden nicht konsistent erfasst und es gibt keine Möglichkeit, Daten über die Besuche auf dem gesamten Campus zu sammeln und zu analysieren. 

Die Campusverwaltung möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

Während dieses Kurses erstellen Sie Anwendungen und führen eine Automatisierung durch, damit das Verwaltungs- und Sicherheitspersonal des Bellows College den Zugang zu den Gebäuden auf dem Campus verwalten und kontrollieren kann. 

In diesem Lab erstellen Sie eine modellgesteuerte Power Apps-App, mit der die Campus-Mitarbeiter im Backoffice  die Besuchsdatensätze für den gesamten Campus verwalten können.

Weiterführende Schritte des Lab
======================

Im Rahmen der Erstellung der modellgesteuerten App führen Sie Folgendes aus:

-   Das Erstellen einer neuen modellgesteuerten App mit dem Namen „Campus Management“

-   Bearbeiten der App-Navigation, um auf die erforderlichen Entitäten zu verweisen

-   Anpassen der Formulare und Ansichten der erforderlichen Entitäten für die App

Wir werden mit folgenden Komponenten arbeiten:

- **Ansichten**: Mithilfe von Ansichten kann der Benutzer die vorhandenen Daten in Form einer
Tabelle anzeigen.

- **Formulare**: Hier erstellt bzw. aktualisiert der Benutzer neue Datensätze in den Entitäten.

Beide werden für eine bessere Benutzererfahrung in die modellgesteuerte App integriert.

## Voraussetzungen

* Beendigung von **Modul 0 Lab 0 – Lab-Umgebung überprüfen**
* Beendigung von **Modul 2 Lab 1 – Einführung in Common Data Service**

Vor dem Beginn zu beachtende Dinge
-----------------------------------

-   Welche Änderungen sollten wir vornehmen, um die Benutzererfahrung zu verbessern?

-   Was sollten wir auf der Grundlage des von uns erstellten Datenmodells in eine modellgesteuerte App aufnehmen?
    
-   Welche Anpassungen können an der Seitenübersicht einer modellgesteuerten App vorgenommen werden?


Übung 1: Ansichten und Formulare anpassen
=======================================

**Ziel:** In dieser Übung passen Sie Ansichten und Formulare der benutzerdefinierten erstellten Entitäten an, die in der modellgesteuerten App verwendet werden.

Aufgabe 1: Formular „Besuch bearbeiten“
-----------------------------------

1.  Melden Sie sich bei <https://make.powerapps.com> an, wenn Sie noch nicht angemeldet sind.

2.  Wählen Sie Ihre **Umgebung** aus.

3.  Wählen Sie **Lösungen** aus.

4.  Klicken Sie, um Ihre **Campusverwaltung**-Lösung zu öffnen.

5.  Klicken Sie, um die Entität **Besuch** zu öffnen.

6.  Wählen Sie die Registerkarte **Formulare** aus, und klicken Sie auf den Formulartyp **Haupt** damit dieser geöffnet wird. 

    -   Standardmäßig hat das Formular zwei Felder: „Name“ (primäres Feld) und „Besitzer“.
    
7.  Fügen Sie unter dem Feld **Besitzer** die folgenden Felder hinzu, indem Sie Felder in das Formular ziehen oder einfach auf Feldnamen klicken:

    * **Gebäude**
    * **Besucher**
    * **Geplanter Start**
    * **Geplantes Ende**
    * **Tatsächlicher Start**
    * **Tatsächliches Ende** 
    
8.  Ziehen Sie das Feld **Code**, und legen Sie es im Formularkopf ab. (Möglicherweise müssen Sie das Eigenschaftenpanel auf der rechten Seite des Bildschirms minimieren, um das Feld im Formular anzuzeigen.)

9.  Aktivieren Sie im weiterhin ausgewählten Codefeld das Kontrollkästchen für **Schreibgeschütztes Feld** im Eigenschaftenpanel.

10.  Wählen Sie das Feld **Besitzer** aus. Ändern Sie im Eigenschaftenpanel die **Feldbezeichnung** in **Host**.

11.  Klicken Sie oben rechts auf **Speichern**, und warten Sie, bis der Speichervorgang abgeschlossen ist.

12.  Klicken Sie oben rechts auf **Veröffentlichen**, und warten Sie, bis die Veröffentlichung abgeschlossen ist.

13.  Klicken Sie oben links im Bildschirm auf **Zurück**. Sie sollten jetzt wieder auf der
     Formular-Registerkarte „Entität Besuch“.

## Aufgabe 2: Besuchsansichten bearbeiten

In dieser Aufgabe ändern wir die Standardansicht „Aktive Besuche“ und erstellen eine neue Ansicht für die heutigen Besuche.

1.  Wählen Sie die Registerkarte **Ansichten** aus, und klicken Sie auf die Ansicht **Aktive Besuche**, um diese zu öffnen.

2.  Fügen Sie der Ansicht die folgenden Felder hinzu, indem Sie entweder auf die Felder klicken oder sie ziehen und ablegen:

    *  **Code**
    *  **Besucher**
    *  **Gebäude**
    *  **Geplanter Start** 
    *  **Geplantes Ende**
    
3.  Klicken Sie auf die Spalte **Erstellt am**, und wählen Sie **Entfernen** aus. Das Feld **Erstellt am** wird nun aus der Ansicht entfernt.

4.  Klicken Sie auf die Spalte **Name**, und wählen Sie dann **Entfernen** aus. Das Feld **Name** wird nun aus der Ansicht entfernt.

5.  Klicken Sie im Eigenschaftenpanel rechts auf **Sortieren nach...**, und wählen Sie **Geplanter Start** aus. Klicken Sie erneut auf **Geplanter Start**, um die Reihenfolge in „absteigend“ zu ändern (neue Besuche oben).

6.  Passen Sie die Größe der einzelnen Spaltenbreiten an die Daten an.

7.  Klicken Sie auf **Speichern** und warten Sie, bis die Änderungen gespeichert sind.

8.  Klicken Sie auf **Veröffentlichen** und warten Sie, bis die Veröffentlichung abgeschlossen ist.

9.  Jetzt werden wir die Ansicht klonen, um eine neue Ansicht für die heutigen Besuche zu erstellen.

10.  Klicken Sie auf den Dropdownpfeil neben der Schaltfläche **Speichern** (achten Sie darauf, dass Sie nicht die Schaltfläche selbst drücken), und wählen Sie **Speichern unter** aus.

11.  Ändern Sie den Namen in **Heutige Besuche** und drücken Sie auf **Speichern**.

12.  Drücken Sie im Eigenschaftenpanel auf den Link **Filter bearbeiten**.

13.  Klicken Sie auf **Hinzufügen**, und wählen Sie **Zeile hinzufügen** aus.

14.  Wählen Sie **Geplanter Start** als Feld aus, und wählen Sie dann **Heute** als Bedingung aus. 

15.  Klicken Sie in der Zeile **Status** auf **...**, und klicken Sie **Löschen**. 

16.  Die Ansicht wird jetzt gefiltert, um nur Datensätze anzuzeigen, bei denen das geplante Startdatum heute liegt. Klicken Sie auf **OK**, um die Bedingung zu speichern.

15.  Fügen Sie der Ansicht die Felder **Tatsächlicher Start** und **Tatsächliches Ende** hinzu. 

        > **Hinweis:** Da wir nicht mehr nach dem Ansichtsstatus filtern, erhalten wir alle heutigen Besuche, einschließlich der abgeschlossenen. Diese Felder helfen dabei, zwischen abgeschlossenen und laufenden Besuchen zu unterscheiden.

16.  Klicken Sie auf **Speichern** und warten Sie, bis die Änderungen gespeichert sind.

17.  Klicken Sie auf **Veröffentlichen** und warten Sie, bis die Veröffentlichung abgeschlossen ist.


Übung Nr. 2: Eine modellgesteuerte Anwendung erstellen
=============================================

**Ziel:** In dieser Übung erstellen Sie die modellgesteuerte App, passen die Sitemap an und testen die App.

> Beim Erstellen Ihrer Anwendung werden mehrere Felder angezeigt, um die Sie sich nicht gekümmert haben, insbesondere bei den Schritten für die Siteübersicht. Für die Labs haben wir einige Abkürzungen vorgenommen. In einer realen Implementierung würden Sie diesen Elementen logische Namen geben.

Aufgabe Nr. 1: Eine Anwendung erstellen
----------------------------

1.  Öffnen Sie soweit noch nicht geschehen die Campusverwaltung-Lösung.

    -   Anmelden bei <https://make.powerapps.com>

    -   Während Sie in Ihrer Umgebung sind, klicken Sie auf Ihre **Campusverwaltung**-Lösung,
        um sie zu öffnen.
    
2.  Eine modellgesteuerte Anwendung erstellen

    -   Klicken Sie auf **Neu**, und wählen Sie **App** und dann **modellgesteuerte App** aus. Dadurch wird eine neue Registerkarte geöffnet.
    
    -   Aktivieren Sie das Kontrollkästchen **Vorhandene Lösung zum Erstellen der App verwenden** aus
    
    -   Geben Sie als Name **[Ihr Nachname] Campusverwaltung** ein, und klicken Sie auf **Weiter**.
    
    -   Wählen Sie Ihre Campusverwaltung-Lösung aus
    
    -   Klicken Sie auf **Fertig**
    
3.  Klicken Sie auf das Stiftsymbol neben **Siteübersicht.**

4.  Bearbeiten Sie die Standardtitel

    -   Wählen Sie **Neuer Bereich** aus.

    -   Ändern Sie den Titel von „Neuer Bereich“ im Eigenschaftenbereich rechts in **Campus**.

    -   Wählen Sie **Neue Gruppe** aus.

    -   Ändern Sie den Titel von „Neue Gruppe“ im Eigenschaftenbereich rechts in **Sicherheit**.
    
5.  Die Entität „Kontakt“ zur Siteübersicht

    -   Wählen Sie **Neuer Unterbereich** aus.

    -   Wählen Sie im Bereich **Eigenschaften** die Option **Entität** aus der Dropdownliste aus
        als **Typ** aus.

    -   Suchen Sie nach der Entität **Kontakt** aus der Dropdownliste für **Entität**.
    
6.  Fügen Sie der Siteübersicht die Entität „Besuch“ hinzu

    -   Wählen Sie die Gruppe **Sicherheit** aus, und klicken Sie auf **Hinzufügen**.

    -   Wählen Sie **Teilbereich** aus.

    -   Gehen Sie zum Bereich **Eigenschaften**.

    -   Wählen Sie **Entität** aus der Dropdownliste für **Typ** aus, und suchen Sie nach
        **Besuch**-Entität aus der Dropdown-Liste für **Entität**.
    
7.  Fügen Sie der Siteübersicht die Entität „Gebäude“ hinzu

    -   Wählen Sie den **Campus**-Bereich aus, und klicken Sie auf **Hinzufügen**.
    
    -   Wählen Sie **Gruppieren** aus.
    
    -   Geben Sie **Einstellungen** als den **Titel** im Bereich **Eigenschaften** ein.
    
    -   Klicken Sie bei ausgewählter Option im Bereich **Einstellungen** auf **Hinzufügen**.
    
    -   Wählen Sie **Teilbereich** aus.
    
    -   Gehen Sie zum Bereich **Eigenschaften**.
    
    -   Wählen Sie **Entität** aus der Dropdownliste für **Typ** aus, und suchen Sie in der Dropdownliste **Entität** nach der Entität **Gebäude**.

8.  Klicken Sie auf **Speichern**. Während des Speicherns der Änderungen wird das Ladebild angezeigt.

9.  Klicken Sie auf **Veröffentlichen**, und warten Sie, bis die Veröffentlichung der Siteübersicht abgeschlossen ist.

10.  Klicken Sie auf **Speichern und schließen**, um den Siteübersicht-Editor zu schließen.

11.  Sie sehen, dass die Assets für die Entitäten, die der Siteübersicht hinzugefügt wurden,
     sich jetzt alle in der Anwendung befinden.
     
12.  Klicken Sie auf **Speichern**, um die Anwendung zu speichern.

13.  Klicken Sie auf **Überprüfen**, um die in der Anwendung vorgenommenen Änderungen zu überprüfen. 

        > Es werden einige Warnungen angezeigt, die wir aber ignorieren können, da wir nicht auf eine bestimmte Ansicht und ein bestimmtes Formular für die Entitäten verwiesen haben und die Benutzer Zugriff auf alle Ansichten und Formulare für die Entitäten **Besuch** und **Gebäude** haben.

14.  Klicken Sie auf **Veröffentlichen**, um die Anwendung zu veröffentlichen und auf den Abschluss des Veröffentlichungsvorgangs
     
     
15.  Klicken Sie auf **Speichern und schließen**, um den App-Designer zu schließen.

16.  Klicken Sie auf **Fertig**.

17.  Wählen Sie **Lösungen** und **Alle Anpassungen veröffentlichen** aus.

18.  Wählen Sie **Apps** aus. Ihre Anwendung sollte jetzt aufgelistet werden.

Aufgabe 2: Testanwendung
--------------------------

1.  Starten Sie die Anwendung

    -   Wählen Sie **Apps** aus, und klicken Sie auf Ihre **Campusverwaltung**-App. (Wenn Sie Ihre App anfangs nicht sehen, müssen Sie möglicherweise Ihren Browser aktualisieren.)

    -   Die Anwendung sollte in einem neuen Fenster geöffnet werden.
    
2.  Erstellen eines neuen Kontaktdatensatzes

    -   Die App sollte mit der Ansicht **Aktive Kontakte** geöffnet werden

    -   Klicken Sie im oberen Menü auf **Neu**.

    -   Geben Sie als **Vorname** `John` und als **Nachname** `Doe` an.

    -   Geben Sie unter **E-Mail** Ihre persönliche E-Mail-Adresse an. Dies wird in einem zukünftigen Lab verwendet. 
    
    -   Klicken Sie auf **Speichern und schließen**.

    -   Sie sollten nun den erstellten Kontakt in der Ansicht **Aktive Kontakte** sehen.
    
3.  Erstellen eines neuen Gebäudedatensatzes

    -   Wählen Sie aus der Siteübersicht **Gebäude** aus.

    -   Klicken Sie auf **Neu**.

    -   Geben Sie als **Name** `Microsoft Building` ein.
        
    -   Klicken Sie auf **Speichern und schließen**, damit der neu erstellte Datensatz in
        in der Ansicht „Aktive Gebäude“ angezeigt wird.
    
4.  Erstellen eines neuen Besuchsdatensatzes

    -   Wählen Sie **Besuche** in der Siteübersicht aus.
    
    -   Klicken Sie auf **Neu**.
    
    -   Füllen Sie die Felder folgendermaßen aus: 
    
        -   **Name**: `Neuer Testbesuch`
        -   **Gebäude**: Wählen Sie Microsoft Building
        -   **Besucher**: Wählen Sie Max Mustermann aus
        -   **Geplanter Start**: Wählen Sie das morgige Datum und 14:00 Uhr als Startzeit aus
        -   **Geplantes Ende**: Wählen Sie das morgige Datum und 15:30 Uhr als Endzeit aus
        
    -   Klicken Sie auf **Speichern und schließen**. Dadurch wird der Datensatz erstellt und Sie sollten ihn auf der
        Ansicht „Aktive Besuche“.
        
    -   Ändern Sie die Ansicht in **Heutige Besuche**. Sie sollten den neuen Besuch in der Ansicht anzeigen können.
    
5. Sie können weitere Testdatensätze hinzufügen.

   Ihre ausgeführte App sollte ungefähr so aussehen:

![Beispiel einer modellgesteuerten App](media/3-model-app.png)

# Herausforderungen

* Spezifische Ansichten und Formulare für Besuche und Gebäude auswählen
* Das Sicherheitspersonal arbeitet üblicherweise in einem einzigen Gebäude. Welche einfache Möglichkeit könnten Sie ihnen bieten, Besuche nur für ein ausgewähltes Gebäude anzuzeigen?
* Den Zugriff auf bestimmte Entitäten beschränken, z. B. sollte „Gebäude“ für alle Mitarbeiter außer den Administratoren schreibgeschützt sein
* Welche Dashboards würden Sie der App hinzufügen?
