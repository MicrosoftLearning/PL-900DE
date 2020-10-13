---
lab:
    title: 'Lab: Power Automate'
    module: 'Modul 4: Erste Schritte mit Power Automate'
---

# Modul 4: Erste Schritte mit Power Automate
## Lab: Power Automate

Szenario
========

Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus. Campusbesucher werden derzeit auf Papier erfasst. Die Informationen werden nicht konsistent erfasst und es gibt keine Möglichkeit, Daten über die Besuche auf dem gesamten Campus zu sammeln und zu analysieren. 

Die Campusverwaltung möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

Während dieses Kurses erstellen Sie Anwendungen und führen eine Automatisierung durch, damit das Verwaltungs- und Sicherheitspersonal des Bellows College den Zugang zu den Gebäuden auf dem Campus verwalten und kontrollieren kann. 

In diesem Lab erstellen Sie Power Automate-Flows, um verschiedene Aspekte des Campusmanagements zu automatisieren. 

Weiterführende Schritte des Lab
======================

Die folgenden Anforderungen wurden festgelegt, die Sie implementieren müssen, um das Projekt abzuschließen:

* Der jedem Besucher zugewiesene eindeutige Code muss diesem vor seinem Besuch zur Verfügung gestellt werden.
* Das Sicherheitspersonal muss Benachrichtigungen erhalten, dass Besucher ihre geplanten Zeitfenster überschreiten.

## Voraussetzungen

* Abschluss von Lab 1 – Datenmodellierung
* Campus Staff App erstellt in Teil 1 von Lab 2 – Canvas-App (zum Testen)

Vor dem Beginn zu beachtende Dinge
-----------------------------------

-   Welches ist der am besten geeignete Verteilungsmechanismus für die Besuchercodes?
-   So können Überschreitungen gemessen und strenge Richtlinien durchgesetzt werden.

Übung 1: Einen Besuchsbenachrichtigungsfluss erstellen
===============================

**Ziel:** In dieser Übung erstellen Sie einen Power Automate-Flow, der die Anforderung implementiert. Die Besuchsbenachrichtigung erfolgt per E-Mail. Die Benachrichtigung enthält den eindeutigen Code, der dem Besuch zugewiesen ist.

Aufgabe 1: Flow erstellen
---------------------------

1.  Öffnen Sie die Campus Management-Lösung.

    -   Anmelden bei <https://make.powerapps.com>

    -   Wählen Sie Ihre **Umgebung** aus.

    -   Wählen Sie **Lösungen** aus.

    -   Klicken Sie, um die **Campus Management**-Lösung zu öffnen.

2.  Klicken Sie auf  **Neu** und wählen Sie  **Flow** aus. Dadurch wird der Flow-Editor in einem neuen Fenster geöffnet.

3. Suchen Sie nach **Aktuell** und wählen Sie **Common Data Service (aktuelle Umgebung)** aus.

4. Wählen Sie den Trigger **Wenn ein Datensatz erstellt**, **aktualisiert** oder **gelöscht** wird.

   * Wählen Sie**Erstellen** für **Triggerbedingung**
   * Wählen Sie **Besuche** als **Entitätsnamen** aus
   * Wählen Sie im **Bereich** **Organisation** aus

5.  Klicken Sie auf **Neuer Schritt**. Dieser Schritt ist erforderlich, um Besucherinformationen einschließlich der E-Mail-Adresse abzurufen.

6. Suchen Sie nach **Aktuell** und wählen Sie **Common Data Service (aktuelle Umgebung)** aus.

7. Wählen Sie die Aktion **Datensatz abrufen** aus. 

   * Wählen Sie **Kontakte** als **Entitätsname** aus
   * Wählen Sie im Feld **Artikel-ID** aus der Liste für dynamische Inhalte **Besucher (Wert)** aus.

8. Klicken Sie auf **Neuer Schritt**. Dies ist der Schritt, in dem eine E-Mail erstellt und an den Besucher gesendet wird.

9. Suchen Sie nach *E-Mail*, wählen Sie den **E-Mail**-Connector und dann die Aktion **E-Mail-Benachrichtigung senden** aus. 
   * Wenn Sie aufgefordert werden, die Nutzungsbedingungen für diese Aktion anzunehmen, klicken Sie auf **Annehmen**.
   
   * Wählen Sie in der Liste für dynamische Inhalte das Feld **An** und **E-Mail** aus.

   * Geben Sie **Ihr geplanter Besuch am Bellows College** in das Feld **Betreff** ein.

   * Geben Sie den folgenden Text unter **E-Mail-Text** ein.  
        *Hinweis: Dynamischer Inhalt muss dort platziert werden, wo Felder in Klammern angegeben sind. Es wird empfohlen, zuerst den gesamten Text einzugeben und dann an der richtigen Stelle dynamischen Inhalt hinzuzufügen.*

   ```
    Hallo {First Name},

    Sie sind derzeit für den Besuch des Bellows Campus von {Scheduled Start} bis {Scheduled End} vorgesehen.

    Ihr Sicherheitscode lautet {Code}. Bitte geben Sie ihn nicht weiter. Sie müssen diesen Code während Ihres Besuchs erzeugen.


    Mit freundlichen Grüßen

    Campusverwaltung
    Bellows College
   ```
   
10.  Wählen Sie den Flownamen **Unbenannt** aus, und benennen Sie ihn in **Benachrichtigung aufrufen** um.

11.  Wählen Sie **Speichern** aus

Aufgabe 2: Flow überprüfen und aktivieren
--------------------------------

1.  Öffnen der App **Campus-Mitarbeiter**, die Sie erstellt haben 
2.  Drücken Sie „+“, um einen neuen Datensatz hinzuzufügen.
3.  Geben Sie die erforderlichen Informationen ein und klicken Sie auf **Speichern**.
4.  Öffnen Sie den Flow, suchen und öffnen Sie die letzte **Ausführung**.
5.  Öffnen Sie den Schritt **Mail** und überprüfen Sie, ob der E-Mail-Inhalt korrekt generiert wurde.

# Übung Nr. 2: Erstellen eines Security Sweep-Flows

**Ziel:** In dieser Übung erstellen Sie einen Power Automate-Flow, der die Anforderung implementiert. Die Sicherheitsüberprüfung wird alle 15 Minuten durchgeführt und die Sicherheit wird benachrichtigt, wenn einer der Besucher seine geplante Zeit überschritten hat.

## Aufgabe Nr. 1: Einen Flow zum Abrufen von Datensätzen erstellen

1. Öffnen Sie die Campus Management-Lösung.

   -   Anmelden bei <https://make.powerapps.com>

   -   Wählen Sie Ihre **Umgebung** aus.

   -   Wählen Sie **Lösungen** aus.

   -   Klicken Sie, um die **Campus Management**-Lösung zu öffnen.

2. Klicken Sie auf  **Neu** und wählen Sie  **Flow** aus. Dadurch wird der Flow-Editor in einem neuen Fenster geöffnet.

3. Suchen Sie nach *Wiederholung*, wählen Sie **Konnektor planen** und anschließend den Trigger **Wiederholung** aus.

4. **Intervall** auf **15 Minuten** einstellen

5. Klicken Sie auf **Neuer Schritt**. Suchen Sie nach **Aktuell** und wählen Sie **Common Data Service (aktuelle Umgebung)** aus. Wählen Sie die Aktion **Datensätze auflisten**.

   * Geben Sie unter **Entitätsname** **Besuche** ein
   
   * Klicken Sie auf **Erweiterte Optionen anzeigen**.

   * Den folgenden Ausdruck als **Filterabfrage** eingeben

     ```
     statecode eq 0 and bc_actualstart ne null and bc_actualend eq null and Microsoft.Dynamics.CRM.OlderThanXMinutes(PropertyName='bc_scheduledend',PropertyValue=15)
     ```

   Schrittweise Erklärung

   * `statecode eq 0` filtert aktive Besuche (wobei „Status“ gleich „Aktiv“ ist)
   * `bc_actualstart ne null` beschränkt die Suche auf Besuche, bei denen „Tatsächlicher Start“ einen Wert hat, d. h. es wurde eingecheckt
   * `bc_actualend eq null` beschränkt die Suche auf Besuche, bei denen kein Auschecken stattgefunden hat („Tatsächliches Ende“ hat keinen Wert) 
   * `Microsoft.Dynamics.CRM.OlderThanXMinutes (PropertyName = 'bc_scheduledend', PropertyValue = 15)` beschränkt Besuche, die vor mehr als 15 Minuten abgeschlossen werden sollten.  

6.  Klicken Sie auf **Neuer Schritt**. Such Sie nach **Anwenden**, und wählen Sie Aktion **Auf jedes anwenden** aus. 

7.  Wählen Sie aus den dynamischen Inhalten **Wert** im Feld **Eine Ausgabe aus vorherigen Schritten auswählen** aus.

8.  Gebäudedaten für zugehörigen Datensatz abrufen

    * Klicken Sie innerhalb der Schleife auf **Aktion hinzufügen**.
    * Suchen Sie nach **Aktuell** und wählen Sie **Common Data Service (aktuelle Umgebung)** aus. 
    * Wählen Sie die Aktion **Datensatz abrufen** aus.
    * Klicken Sie auf die Schaltfläche mit den drei Punkten (...) neben **Datensatz abrufen**, und wählen Sie **Umbenennen** aus. Geben Sie als Schrittname **GetBuilding** ein.
    * Wählen Sie **Gebäude** als **Entitätsname** aus
    * Wählen Sie **Gebäude (Wert)** als **Artikel-ID** aus dem dynamischen Inhalt aus.

9.  Besucherdaten für zugehörigen Datensatz abrufen

    * Klicken Sie innerhalb der Schleife auf **Aktion hinzufügen**.
    * Suchen Sie nach **Aktuell** und wählen Sie **Common Data Service (aktuelle Umgebung)** aus. 
    * Wählen Sie die Aktion **Datensatz abrufen** aus.
    * Klicken Sie auf die Schaltfläche mit den drei Punkten (...) neben **Datensatz abrufen**, und wählen Sie **Umbenennen** aus. Geben Sie als Schrittname **GetVisitor** ein.
    * Wählen Sie **Besuche** als **Entitätsname** aus.
    * Wählen Sie **Besucher (Wert)** als **Artikel-ID** aus dem dynamischen Inhalt aus.
    
10.  Eigentümerdaten für zugehörigen Datensatz abrufen

* Klicken Sie innerhalb der Schleife auf **Aktion hinzufügen**.
* Suchen Sie nach **Aktuell** und wählen Sie **Common Data Service (aktuelle Umgebung)** aus. 
* Wählen Sie die Aktion **Datensatz abrufen** aus.
* Klicken Sie auf die Schaltfläche mit den drei Punkten (...) neben **Datensatz abrufen**, und wählen Sie **Umbenennen** aus. Geben Sie als Schrittname **GetUser** ein.
* Wählen Sie **Besuche** als **Entitätsname** aus.
* Wählen Sie **Eigentümer (Wert)** als **Artikel-ID** aus dem dynamischen Inhalt aus.

11.  Fügen Sie die Aktion **E-Mail-Benachrichtigung senden** aus **Mail**-Verbindung hinzu, und bleiben Sie dabei innerhalb der Aktion **Auf jede Schleife anwenden**.

12.  Ihre E-Mail-Adresse als **An** eingeben

13.  Geben Sie „Kontakt {**Besucher (Wert)**} hat seinen Empfang überschritten“ in das Feld **Betreff** ein. **Besucher (Wert)** ist ein dynamischer Inhalt aus dem Schritt **GetVisitor**.

14.  Geben Sie „Es ist im Gebäude {**Name**} passiert“ in das Feld **Körper** ein. **Name** ist ein dynamischer Inhalt des Schritts **GetBuilding**.

15.  Klicken Sie auf **Erweiterte Optionen anzeigen**.

16.  **Erste Email** aus dem Schritt **GetUser** lokalisieren und in das CC-Feld einfügen (der Besprechungsleiter erhält eine Kopie der E-Mail)

17.  Wählen Sie den Flownamen **Unbenannt** in der oberen linken Ecke aus, und benennen Sie ihn in **Sicherheits-Sweep** um.

16.  Wählen Sie **Speichern** aus

## Aufgabe 2: Flow überprüfen und aktivieren

1. Suchen oder erstellen Sie Besuchsdatensätze mit
   1. Aktivem Status
   2. Geplantem Ende in der Vergangenheit (über 15 Minuten)
   3. Wert für „Tatsächlicher Start“
2. Navigieren Sie zu Ihrer Lösung, und suchen Sie den Flow **Sicherheits-Sweep**. Klicken Sie auf die Schaltfläche mit den drei Punkten (...) und dann auf **Bearbeiten**.
3. Wenn Ihr Flow geöffnet wird, klicken Sie auf **Test**.
4. Wählen Sie **Ich werde die Triggeraktion ausführen** aus.
5. Klicken Sie auf **Test** und dann auf **Flow ausführen**.
6. Wenn der Flow abgeschlossen ist, klicken Sie auf **Fertig**. 
7. Erweitern Sie zuerst die Schritte **Auf alle anwenden** und dann **E-Mail-Benachrichtigung senden**. Überprüfen Sie die Werte **Betreff**, **E-Mail-Text**. Erweitern Sie **Mehr anzeigen**, und überprüfen Sie den Wert **CC**.
8. Navigieren Sie zur Lösung, klicken Sie auf die Schaltfläche mit den drei Punkten (...) neben dem Flow, und wählen Sie **Deaktivieren** aus. Dies soll verhindern, dass der Datenfluss nach einem Zeitplan auf dem Testsystem ausgeführt wird.

# Herausforderungen

* Erstellungsinformationen hinzufügen und dem Benachrichtigungsflow zuordnen.
* Können Sie einen Barcode für den Besuchscode generieren? Wann könnte das nützlich sein?
* Wie kann eine benutzerfreundliche Datumsformatierung im E-Mail-Text sichergestellt werden?
* Ist es möglich, eine Tabelle mit Übernachtungsinformationen zu erstellen und nur eine einzige E-Mail zu senden?
