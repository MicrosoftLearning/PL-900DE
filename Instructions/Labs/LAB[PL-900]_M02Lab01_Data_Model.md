---
lab:
    title: 'Lab 1: Datenmodellierung'
    module: 'Modul 2: Einführung in Common Data Service'
---

# Modul 2: Einführung in Common Data Service
## Lab: Datenmodellierung


# Szenario

Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus. Campusbesuche werden derzeit in Papierzeitschriften aufgezeichnet. Die Informationen werden nicht konsistent erfasst und es gibt keine Möglichkeit, Daten über die Besuche auf dem gesamten Campus zu sammeln und zu analysieren. 

Die Campusverwaltung möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

Während dieses Kurses erstellen Sie Anwendungen und führen eine Automatisierung durch, damit das Verwaltungs- und Sicherheitspersonal des Bellows College den Zugang zu den Gebäuden auf dem Campus verwalten und kontrollieren kann. 

In diesem Lab greifen Sie auf Ihre Umgebung zu, erstellen eine CDS-Datenbank (Common Data Service) und eine Lösung zum Nachverfolgen Ihrer Änderungen. Sie erstellen auch ein Datenmodell, um die folgenden Anforderungen zu unterstützen:

-   R1 –  Verfolgen Sie Standorte (Gebäude) der Campusbesuche
-   R2 –  Aufzeichnen der grundlegende Informationen, um die Besucher zu identifizieren und nachzuverfolgen 
-   R3 – Planen, Aufzeichnen und Verwalten von Besuchen 

Zum Abschluss werden Sie Beispieldaten in Common Data Service importieren.

# Weiterführende Schritte des Lab

Um Ihre Lernumgebungen vorzubereiten, werden Sie:

* eine Lösung und einen Herausgeber erstellen
* sowohl neue als auch vorhandene Komponenten hinzufügen, die zur Erfüllung der Anwendungsanforderungen erforderlich sind. Beschreibungen zu den Metadaten (Entitäten und Beziehungen) finden Sie im [Datenmodelldokument](../../Allfiles/Campus%20Management.png). Sie können die STRG-Taste gedrückt halten oder mit der rechten Maustaste auf den Link klicken, um das Datenmodelldokument in einem neuen Fenster zu öffnen.

Nach Abschluss aller Anpassungen wird Ihre Lösung mehrere Entitäten enthalten:

-   Kontakt
-   Gebäude
-   Besuch

## Voraussetzungen:

* Beendigung von **Modul 0 Lab 0 – Lab-Umgebung bestätigen**

## Bevor Sie beginnen, sollten Sie Folgendes berücksichtigen:

* Namenskonvention

* Datentypen, Einschränkungen (z. B. maximale Länge eines Namens)

* Datetime-Formatierung zur Unterstützung einer einfachen Lokalisierung

# Übung Nr. 1: Lösung erstellen

## Aufgabe Nr. 1: Lösung und Publisher erstellen

1.  Lösung erstellen

    -   Navigieren Sie zu <https://make.powerapps.com>. Möglicherweise müssen Sie sich erneut authentifizieren. Klicken Sie dazu auf **Anmelden**, und folgen Sie den Anweisungen (falls erforderlich).

    -   Wählen Sie Ihre Umgebung aus. Klicken Sie dazu in der oberen rechten Ecke des Bildschirms auf **Umgebung**, und wählen Sie im Dropdownmenü Ihre Umgebung aus.

    -   Wählen Sie **Lösungen** aus dem linken Menü aus, und klicken Sie auf **Neue Lösung**.

    -   Geben Sie **[Ihr Nachname] Campusverwaltung** als **Anzeigename** ein.

2.  Publisher erstellen

    -   Klicken Sie auf das Dropdownmenü **Herausgeber**, und wählen Sie **Herausgeber** aus.

    -   Geben Sie in dem Fenster, das daraufhin eingeblendet wird, **Bellows College** als **Anzeigename** ein. 
    
    -   Geben Sie **bc** als **Präfix** ein.

    -   Klicken Sie auf **Speichern und schließen**.
    
    -   Klicken Sie im Popupfenster auf **Fertig**.

3.  Schließen Sie die Lösungserstellung ab.

    -   Klicken Sie nun auf die Dropdownliste **Publisher**, und wählen Sie den Herausgeber **Bellows College** aus,
        den Sie gerade erstellt haben.

    -   Vergewissern Sie sich, dass **Version** auf **1.0.0.0** gesetzt ist. 
    
    -   Klicken Sie auf **Erstellen**.

## Aufgabe Nr. 2: Eine vorhandene Entität hinzufügen

1.  Klicken Sie, um Ihre **Campusverwaltung**-Lösung, die Sie gerade erstellt haben, zu öffnen.

2.  Klicken Sie auf **Vorhandene hinzufügen**, und wählen Sie **Entität** aus.

3.  Suchen Sie **Kontakt**, und wählen Sie diese Option aus.

4.  Klicken Sie auf **Weiter**.

5.  Klicken Sie unter „Kontakt“ auf **Komponenten auswählen**.

6.  Wählen Sie die Registerkarte **Ansichten** aus, und wählen Sie die Ansicht **Aktive Kontakte** aus. Klicken Sie auf
    **Hinzufügen**.
    
7.  Klicken Sie erneut auf **Komponenten auswählen**.

8.  Wählen Sie die Registerkarte **Formulare** aus, und wählen Sie das Formular **Kontakt**aus.
    
9.  Klicken Sie auf **Hinzufügen**.

    > Sie sollten **1 Ansicht** und **1 Formular** ausgewählt haben. 
    
10.  Klicken Sie erneut auf **Hinzufügen**. Dadurch wird der neu erstellten Lösung die Entität „Kontakt“ mit der ausgewählten Ansicht und dem ausgewählten Formular hinzugefügt. 
    
11.  Ihre Lösung sollte jetzt eine Entität haben: Kontakt.

# Übung Nr. 2: Entitäten und Beziehungen erstellen

**Ziel:** In dieser Übung erstellen Sie Entitäten und fügen Beziehungen
zwischen den Entitäten hinzu.

## Aufgabe Nr. 1: Entität „Gebäude“ und Felder erstellen

1.  In Ihrem Browser sollte weiterhin Ihre Campusverwaltung-Lösung geöffnet sein. Öffnen Sie andernfalls die Lösung wie folgt:

    * Melden Sie sich bei <https://make.powerapps.com> an (falls Sie noch nicht angemeldet sind)
    
    * Wählen Sie **Lösungen** aus, und klicken Sie zum Öffnen der Lösung **[Ihr Nachname] Campusverwaltung**,
          die Sie gerade erstellt haben.
          
2.  Die Entität „Gebäude“ erstellen

    -   Klicken Sie auf **Neu**, und wählen Sie **Entität** aus.
    
    -   Geben Sie **Gebäude** als **Anzeigename** ein. 
    
    -   Klicken Sie auf **Fertig**. Dadurch wird die Entität im Hintergrund bereitgestellt, während Sie damit beginnen können, weitere Entitäten und Felder hinzuzufügen.

## Aufgabe Nr. 2: Erstellen der Entität „Besuch“ und von Feldern

Die Entität **Besuch** wird Informationen zu den Campusbesuchen enthalten, einschließlich des Gebäudes, des Besuchers und des geplanten sowie des tatsächlichen Zeitpunkts jedes Besuchs. 

Wir möchten jedem Besuch eine eindeutige Nummer zuweisen, die von einem Besucher leicht eingegeben und interpretiert werden kann, wenn er beim Einchecken gefragt wird.

> Wir verwenden **zeitzonenunabhängiges** Verhalten beim Aufzeichnen von Datums- und Uhrzeitinformationen, da die Uhrzeit eines Besuchs immer die Ortszeit am Standort des Gebäudes ist und sich nicht ändern sollte, wenn sie in einer anderen Zeitzone angezeigt wird. 

1.  Wählen Sie Ihre **Campusverwaltung**-Lösung aus.

2. Entität „Besuch“ erstellen

   * Klicken Sie auf **Neu**, und wählen Sie **Entität** aus.
   
   * Geben Sie **Besuch** als **Anzeigename** ein. 
   
   * Klicken Sie auf **Fertig**. Dadurch wird die Entität im Hintergrund bereitgestellt, während Sie damit beginnen können, weitere Felder hinzuzufügen.

3. Erstellen Sie das Feldes „Geplanter Start“

   * Stellen Sie sicher, dass Sie die Registerkarte **Felder** ausgewählt haben, und klicken Sie auf **Feld hinzufügen**.
   
   * Geben Sie **Geplanter Start** als **Anzeigename** ein.
   
   * Wählen Sie **Datum und Uhrzeit** als **Datentyp** aus.
   
   * Wählen Sie im Feld **Erforderlich** die Option **Erforderlich** aus.
   
   * Erweitern Sie den Abschnitt **Erweiterte Optionen**.
   
   * Wählen Sie im Feld **Verhalten** den Eintrag **Zeitzonenunabhängig** aus.
   
   * Klicken Sie auf **Fertig**.

4.  Erstellen des Feldes „Geplantes Ende“

    * Klicken Sie auf **Feld hinzufügen**.
    
    * Geben Sie **Geplantes Ende** als **Anzeigename** ein.
    
    * Wählen Sie **Datum und Uhrzeit** als **Datentyp** aus.
    
    * Wählen Sie im Feld **Erforderlich** die Option **Erforderlich** aus.
    
    * Erweitern Sie den Abschnitt **Erweiterte Optionen**.
    
    * Wählen Sie im Feld **Verhalten** den Eintrag **Zeitzonenunabhängig** aus.
    
    * Klicken Sie auf **Fertig**.
    
5.  Erstellen des Feldes „Tatsächlicher Start“

    * Klicken Sie auf **Feld hinzufügen**.
    
    * Geben Sie **Tatsächlicher Start** als **Anzeigename** ein.
    
    * Wählen Sie **Datum und Uhrzeit** als **Datentyp** aus.
    
    * Belassen Sie im Feld **Erforderlich** die Einstellung **Optional**.
    
    * Erweitern Sie den Abschnitt **Erweiterte Optionen**.
    
    * Wählen Sie im Feld **Verhalten** den Eintrag **Zeitzonenunabhängig** aus.
    
    * Klicken Sie auf **Fertig**.
    
6.  Erstellen Sie das Feld „Tatsächliches Ende“

    * Klicken Sie auf **Feld hinzufügen**.
    
    * Geben Sie **Tatsächliches Ende** als **Anzeigename** ein.
    
    * Wählen Sie **Datum und Uhrzeit** als **Datentyp** aus.
    
    * Belassen Sie im Feld **Erforderlich** die Einstellung **Optional**.
    
    * Erweitern Sie den Abschnitt **Erweiterte Optionen**.
    
    * Wählen Sie im Feld **Verhalten** den Eintrag **Zeitzonenunabhängig** aus.
    
    * Klicken Sie auf **Fertig**.
    
7.  Erstellen Sie das Feld „Code“

    * Klicken Sie auf **Feld hinzufügen**.
    
    * Geben Sie **Code** als **Anzeigename** ein.
    
    * Wählen Sie **AutoWert** als **Datentyp** aus.
    
    * Wählen Sie **Datumspräfixnummer** als **AutoWert-Typ** aus.
    
    * Klicken Sie auf **Fertig**.
    
8.  Klicken Sie auf **Entität speichern**

## Aufgabe Nr. 3: Beziehungen erstellen

1.  Stellen Sie sicher, dass Sie weiterhin die Entität **Besuch** Ihrer **Campusverwaltung**-Lösung anzeigen. Navigieren Sie andernfalls dorthin.

2.  Erstellen der Beziehung „Besuch zu Kontakt“

    * Wählen Sie die Registerkarte **Beziehungen** aus.
    
    * Klicken Sie auf **Beziehung hinzufügen**, und wählen Sie **n:1** aus.
    
    * Wählen Sie **Kontakt** als **Verknüpft (Eins)** aus. 
    
    * Geben Sie **Besucher** als **Anzeigename des Nachschlagefelds** ein 
    
    * Klicken Sie auf **Fertig**.
    
3.  Erstellen Sie die Beziehung „Besuch in Gebäude“

    * Klicken Sie auf **Beziehung hinzufügen**, und wählen Sie **n:1** aus.
    
    * Wählen Sie **Gebäude** als **Verknüpft (Eins)** aus. 
    
    * Klicken Sie auf **Fertig**.
    
4.  Klicken Sie auf **Entität speichern**.

5.  Wählen Sie im oberen Menü **Lösungen** aus, und klicken Sie auf **Alle Anpassungen veröffentlichen**.

# Übung Nr. 3: Daten importieren

**Ziel:** In dieser Übung importieren Sie Beispieldaten in die Common Data Service-Datenbank.

## Aufgabe Nr. 1: Lösung importieren

In dieser Aufgabe importieren Sie eine Lösung, die den Power Automate-Flow enthält, der erforderlich ist, um den Datenimport abzuschließen.

1. Die Datei **DataImport_managed.zip** sollten Sie auf Ihrem Desktop gespeichert haben. Laden Sie soweit noch nicht geschehen die [Datenimportlösung](../../Allfiles/DataImport_managed.zip) herunter.

2. Melden Sie sich bei <https://make.powerapps.com> an.

3. Wählen Sie oben rechts Ihre Umgebung ***Meine Initialen* Übung** aus, falls diese noch nicht ausgewählt ist.

4. Wählen Sie im linken Navigationsbereich **Lösungen** aus.

5. Klicken Sie auf **Importieren**, und klicken Sie dann auf **Durchsuchen**. Navigieren Sie zur Datei **DataImport_managed.zip** auf Ihrem Desktop, wählen Sie sie aus, und klicken Sie dann auf **Weiter**.

>   Möglicherweise wird die folgende Meldung angezeigt:
>
>   Es fehlen Abhängigkeiten. Installieren Sie die folgenden Lösungen, bevor Sie diese installieren...
>
>   Diese Meldung bedeutet entweder, dass das Datenmodell nicht vollständig ist, das
>   Herausgeberpräfix nicht **bc** lautet oder für die Entitäten **Gebäude** und **Besuch**
>   andere Namen als in den vorherigen Schritten angegeben sind.

6. Klicken Sie auf **Weiter**. Sie sollten aufgefordert werden, Verbindungen neu herzustellen. 

7. Erweitern Sie die Dropdownliste **Wählen Sie eine Verbindung aus**, und wählen Sie **Neue Verbindung** aus.

8. Es wird ein neues Browserfenster oder eine neue Browserregisterkarte geöffnet. Wählen Sie **Erstellen** aus, wenn Sie aufgefordert werden, eine Common Data Service-Verbindung herzustellen. Falls erforderlich, melden Sie sich an, um das Erstellen der Verbindung abzuschließen.

9. Wechseln Sie zurück zur vorherigen Registerkarte, auf der Sie die Lösung importiert haben.

10. Klicken Sie auf **Aktualisieren**, um die Liste der Verbindungen zu aktualisieren. 

11. Vergewissern Sie sich, dass die Verbindung, die Sie gerade erstellt haben, ausgewählt ist.

12. Klicken Sie auf **Importieren**.

13. Warten Sie, bis der Importvorgang abgeschlossen ist.

## Aufgabe Nr. 2: Daten importieren  

1. Öffnen Sie die **Datenimport**-Lösung.

2. Überprüfen Sie den **Status** des Flows **Daten importieren**.

3. Wenn **Status** auf **Aus** gesetzt ist, klicken Sie auf die Schaltfläche mit den Auslassungspunkten ([...]) neben **Daten importieren**, und wählen Sie dann **Einschalten** aus.

   > **Wichtig:** Wenn eine Fehlermeldung angezeigt wird, überprüfen Sie, ob die von Ihnen erstellten Entitäten und Felder mit den obigen Anweisungen übereinstimmen.

4. Öffnen Sie die Komponente **Daten importieren**. Power Automate wird auf einer neuen Registerkarte geöffnet. 

5. Klicken Sie auf **Los geht's**, wenn ein Popupfenster eingeblendet wird. 

6. Klicken Sie auf **Ausführen**, und klicken Sie dann auf **Flow ausführen**, wenn Sie dazu aufgefordert werden.

7. Klicken Sie auf **Fertig**.

8. Warten Sie, bis die Ausführung der Flow-Instanz abgeschlossen ist. Sie können die Tabelle **28-tägiger Ausführungsverlauf** aktualisieren, um zu sehen, wann der Flow ausgeführt wurde. 

    > Der Zweck dieses Flows bestand darin, Beispieldaten für die nächsten Labs zu generieren. In der nächsten Aufgabe werden Sie überprüfen, ob der Datenimport erfolgreich war. 

## Aufgabe Nr. 3: Datenimport überprüfen

1. Navigieren Sie zurück zur vorherigen Power Apps-Registerkarte. Klicken Sie in dem Popupfenster auf **Fertig**. Wählen Sie in der linken Navigationsleiste **Lösungen** aus, und öffnen Sie Ihre **Campusverwaltung**-Lösung.

2. Klicken Sie, um die Entität **Besuch** zu öffnen, und wählen Sie dann die Registerkarte **Daten** aus.

3. Klicken Sie in der oberen rechten Ecke auf **Aktive Besuche**, um die Ansichtsauswahl einzublenden, und wählen Sie dann **Alle Felder** aus. Dadurch wird die Ansicht geändert, die zum Anzeigen der Besuchsdaten verwendet wird. 

    > Wenn Sie aufgrund geringerer Auflösung **Aktive Besuche** nicht sehen, sollte an derselben Stelle ein Augensymbol angezeigt werden.

    > Wenn der Import erfolgreich war, sollte eine Liste der Besuchseinträge angezeigt werden.

4. Klicken Sie auf einen beliebigen Wert in der Spalte **Gebäude**, und überzeugen Sie sich, dass in einem separaten Fenster das Gebäudeformular geöffnet wird. 

5. Schließen Sie das kürzlich gestartete Fenster.

6. Klicken Sie auf einen beliebigen Wert in der Spalte **Besucher** (möglicherweise müssen Sie dazu nach rechts scrollen), und überzeugen Sie sich, dass in einem separaten Fenster das Kontaktformular geöffnet wird.

7. Schließen Sie das kürzlich gestartete Fenster.

# Herausforderungen

* Würden Sie in Betracht ziehen, die *Termin*-Aktivität als Teil der Lösung zu verwenden? Was würde sich ändern?
* Wie lässt sich erzwingen, dass das geplante Ende hinter dem geplanten Start liegt? 
* Wie lässt sich Unterstützung für mehrere Meetings während eines einzelnen Besuchs hinzufügen?
* Wie lässt sich der Gebäudezugang nicht nur für externe Kontakte, sondern auch für interne Mitarbeiter absichern?
* Wie lässt sich für Besuche in bestimmten Gebäude vorgeben, dass dazu eine Genehmigung der Verwaltung erforderlich ist? Was würde der Genehmigungsprozess im Datenmodell ändern?

