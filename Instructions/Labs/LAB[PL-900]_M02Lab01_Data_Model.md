---
lab:
    title: 'Lab: Datenmodellierung'
    module: 'Modul 2: Einführung in den Common Data Service'
---

# Modul 2: Einführung zu Common Data Service
## Lab: Datenmodellierung


# Szenario
    
Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus. Campusbesuche werden derzeit in Papierzeitschriften aufgezeichnet. Die Informationen werden nicht konsistent erfasst und es gibt keine Möglichkeit, Daten über die Besuche auf dem gesamten Campus zu sammeln und zu analysieren. 

Die Campusverwaltung möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

Während dieses Kurses erstellen Sie Anwendungen und führen eine Automatisierung durch, damit das Verwaltungs- und Sicherheitspersonal des Bellows College den Zugang zu den Gebäuden auf dem Campus verwalten und kontrollieren kann. 

In diesem Lab greifen Sie auf Ihre Umgebung zu, erstellen eine Common Data Service(CDS)-Datenbank und eine Lösung, um Ihre Änderungen nachzuverfolgen. Sie erstellen auch ein Datenmodell, um die folgenden Anforderungen zu unterstützen:

-   R1 –  Verfolgen Sie Standorte (Gebäude) der Campusbesuche
-   R2 –  Aufzeichnen der grundlegende Informationen, um die Besucher zu identifizieren und nachzuverfolgen 
-   R3 – Planen, Aufzeichnen und Verwalten von Besuchen 

Zum Abschluss importieren Sie Beispieldaten in Common Data Service.

# Weiterführende Schritte des Lab

Um Ihre Lernumgebungen vorzubereiten, werden Sie:

* eine Lösung und einen Herausgeber erstellen
* sowohl neue als auch vorhandene Komponenten hinzufügen, die zur Erfüllung der Anwendungsanforderungen erforderlich sind. Die Metadatenbeschreibung (Entitäten und Beziehungen) finden Sie im [Datenmodelldokument](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/Labs/Campus%20Management.png). Sie können die STRG-TASTE gedrückt halten und klicken oder aber mit der rechten Maustaste auf den Link klicken, um das Datenmodelldokument in einem neuen Fenster zu öffnen.

Nach Abschluss aller Anpassungen wird Ihre Lösung mehrere Entitäten enthalten:

-   Kontakt
-   Gebäude
-   Besuch

## Voraussetzungen:

* Abschluss von **Modul 0 Lab 0 – Lab-Umgebung validieren**

## Dinge, die Sie vor Beginn bedenken sollten:

* Namenskonvention
* Datentypen, Einschränkungen (z. B. maximale Länge eines Namens)
* Datetime-Formatierung zur Unterstützung einer einfachen Lokalisierung

# Übung 1: Lösung erstellen

**Ziel:** In dieser Übung bereiten Sie die Umgebung vor und erstellen eine Lösung zur Unterstützung des Datenmodellierungsprozesses. 

## Aufgabe Nr. 1: Lösung und Publisher erstellen

1.  Lösung erstellen

    -   Melden Sie sich bei <https://make.powerapps.com> an. Möglicherweise müssen Sie sich erneut authentifizieren – klicken Sie auf **Anmelden**, und befolgen Sie bei Bedarf die Anweisungen.

    -   Wählen Sie Ihre Umgebung aus, indem Sie in der oberen rechten Ecke des Bildschirms auf **Umgebung** klicken und Ihre Umgebung aus dem Dropdownmenü auswählen.

    -   Wählen Sie **Lösungen** aus dem linken Menü aus, und klicken Sie auf **Neue Lösung**.

    -   Geben Sie [Ihr Nachname] **Campusmanagement** als **Anzeigename** ein.

2.  Publisher erstellen

    -   Klicken Sie auf das Dropdownmenü **Herausgeber**, und wählen Sie **Herausgeber** aus.

    -   In dem sich öffnenden Fenster geben Sie **Bellows College** als **Anzeigename** und **bc** als **Präfix** ein.

    -   Klicken Sie auf **Speichern und schließen**. 
    
    -   Klicken Sie im Popupfenster auf **Fertig**.

3.  Schließen Sie die Lösungserstellung ab.

    -   Klicken Sie nun auf die Dropdownliste **Publisher**, und wählen Sie den Herausgeber **Bellows College** aus,
        den Sie gerade erstellt haben.

    -   Bestätigen Sie, dass die **Version** auf **1.0.0.0** gesetzt ist. 
    
    -   Klicken Sie auf **Erstellen**.

## Aufgabe Nr. 2: Eine vorhandene Entität hinzufügen

1.  Klicken Sie, um Lösung **Campusmanagement** zu öffnen, die Sie gerade erstellt haben.
2.  Klicken Sie auf **Vorhandene hinzufügen**, und wählen Sie **Entität** aus.
3.  Suchen Sie **Kontakt**, und wählen Sie diese Option aus.
4.  Klicken Sie auf **Weiter**.
5.  Klicken Sie auf **Komponenten auswählen**.
6.  Wählen Sie die Registerkarte **Ansichten** aus, und wählen Sie die Ansicht **Aktive Kontakte** aus. Klicken Sie auf
    **Hinzufügen**.
7.  Klicken Sie erneut auf **Komponenten auswählen**.
8.  Wählen Sie die Registerkarte **Formulare** aus, und wählen Sie das Formular **Kontakt**aus.
9.  Klicken Sie auf **Hinzufügen**.
10. Sie sollten **1 Ansicht** und **1 Formular** ausgewählt haben. Klicken Sie auf **Hinzufügen**.
    Dadurch wird die Kontaktentität mit der ausgewählten Ansicht und dem ausgewählten Formular zur neu erstellten Lösung hinzugefügt. 
11.  Ihre Lösung sollte jetzt eine Entität haben: Kontakt.

# Übung Nr. 2: Entitäten und Beziehungen erstellen

**Ziel:** In dieser Übung erstellen Sie Entitäten und fügen Beziehungen
zwischen den Entitäten hinzu.

## Aufgabe Nr. 1: Entität „Gebäude“ und Felder erstellen

1.  In Ihrem Browser sollte weiterhin die Campusmanagement-Lösung geöffnet sein. Öffnen Sie andernfalls die Campusmanagement-Lösung wie folgt:
    * Melden Sie sich bei <https://make.powerapps.com> an (falls Sie noch nicht angemeldet sind)
    * Wählen Sie **Lösungen** aus, und klicken Sie zum Öffnen auf die Lösung **Campus Management**,
          die Sie gerade erstellt haben.
2.  Die Entität „Gebäude“ erstellen

    -   Klicken Sie auf **Neu**, und wählen Sie **Entität** aus.
    -   Geben Sie **Gebäude** als **Anzeigename** ein.  
    -   Klicken Sie auf **Fertig**. Dadurch startet
            die Bereitstellung der Entität im Hintergrund, während Sie mit dem Hinzufügen
            weiterer Entitäten und Felder beginnen können.

## Aufgabe 2: Erstellen der Entität „Besuch“ und von Feldern

Die Entität **Besuch** enthält Informationen zu den Campusbesuchen, einschließlich des Gebäudes, des Besuchers und des geplanten sowie des tatsächlichen Zeitpunkts jedes Besuchs. 

Wir möchten jedem Besuch eine eindeutige Nummer zuweisen, die von einem Besucher leicht eingegeben und interpretiert werden kann, wenn er beim Einchecken gefragt wird.

> [HINWEIS]
> Wir nutzen **zeitzonenunabhängiges** Verhalten beim Aufzeichnen von Datums- und Uhrzeitinformationen, da die Uhrzeit eines Besuchs *immer* die Lokalzeit am Standort des Gebäudes ist und sich nicht ändern sollte, wenn sie aus einer anderen Zeitzone angezeigt wird. 

1.  Wählen Sie Ihre Lösung **Campusmanagement** aus.
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
   * Wählen Sie im Feld **Verhalten** die Option **Zeitzonenunabhängig** aus.
   * Klicken Sie auf **Fertig**.

4.  Erstellen des Feldes „Geplantes Ende“

    * Klicken Sie auf **Feld hinzufügen**.
    * Geben Sie **Geplantes Ende** als **Anzeigename** ein.
    * Wählen Sie **Datum und Uhrzeit** als **Datentyp** aus.
    * Wählen Sie im Feld **Erforderlich** die Option **Erforderlich** aus.
    * Erweitern Sie den Abschnitt **Erweiterte Optionen**.
    * Wählen Sie im Feld **Verhalten** die Option **Zeitzonenunabhängig** aus.
    * Klicken Sie auf **Fertig**.
    
6.  Erstellen des Feldes „Tatsächlicher Start“

    * Klicken Sie auf **Feld hinzufügen**.
    * Geben Sie **Tatsächlicher Start** als **Anzeigename** ein.
    * Wählen Sie **Datum und Uhrzeit** als **Datentyp** aus.
    * Erweitern Sie den Abschnitt **Erweiterte Optionen**.
    * Wählen Sie im Feld **Verhalten** die Option **Zeitzonenunabhängig** aus.
    * Klicken Sie auf **Fertig**.
    
7.  Erstellen Sie das Feld „Tatsächliches Ende“

    * Klicken Sie auf **Feld hinzufügen**.
    * Geben Sie **Tatsächliches Ende** als **Anzeigename** ein.
    * Wählen Sie **Datum und Uhrzeit** als **Datentyp** aus.
    * Erweitern Sie den Abschnitt **Erweiterte Optionen**.
    * Wählen Sie im Feld **Verhalten** die Option **Zeitzonenunabhängig** aus.
    * Klicken Sie auf **Fertig**.
    
7.  Erstellen Sie das Feld „Code“

    * Klicken Sie auf **Feld hinzufügen**.
    * Geben Sie **Code** als **Anzeigename** ein.
    * Wählen Sie **AutoWert** als **Datentyp** aus.
    * Wählen Sie **Datumspräfixnummer** als **AutoWert-Typ** aus.
    * Klicken Sie auf **Fertig**.
    
8.  Klicken Sie auf **Entität speichern**

## Aufgabe 3: Beziehungen erstellen

1.  Vergewissern Sie sich, dass immer noch die Entität **Besuch** Ihrer Lösung **Campusmanagement** angezeigt wird. Navigieren Sie andernfalls dorthin.
2.  Erstellen der Beziehung „Besuch zu Kontakt“
    * Wählen Sie die Registerkarte **Beziehungen** aus.
    * Klicken Sie auf **Beziehung hinzufügen**, und wählen Sie **n:1** aus.
    * Wählen Sie  **Kontakt** für **Verknüpft (Eins)** aus. 
    * Geben Sie **Besucher** als **Anzeigename des Nachschlagefelds** ein 
    * Klicken Sie auf **Fertig**.
3.  Erstellen Sie die Beziehung „Besuch in Gebäude“
    * Klicken Sie auf **Beziehung hinzufügen**, und wählen Sie **n:1** aus.
    * Wählen Sie **Gebäude** für **Verknüpft (Eins)** aus. 
    * Klicken Sie auf **Fertig**.
4.  Klicken Sie auf **Entität speichern**.
5.  Wählen Sie aus dem oberen Menü **Lösungen** aus, und klicken Sie auf **Alle Anpassungen veröffentlichen**.

# Übung Nr. 3: Daten importieren

**Ziel:** In dieser Übung importieren Sie Beispieldaten in die Common Data Service-Datenbank.

## Aufgabe Nr. 1: Datenzuordnung importieren

1. Laden Sie [CampusDataMap.xml](../../Allfiles/Labs/CampusDataMap.xml) herunter, falls Sie dies noch nicht getan haben.
2. Navigieren Sie zum Power Platform Admin Center unter <https://admin.powerplatform.microsoft.com>, und melden Sie sich an.
3. Wählen Sie Ihre Bellows College-Umgebung aus.
4. Klicken Sie oben auf **Einstellungen**.
5. Erweitern Sie den Abschnitt **Datenverwaltung**, und wählen Sie dann **Datenzuordnungen** aus. Dadurch wird der Bildschirm „Zuordnung importieren“ auf einer neuen Browserregisterkarte geöffnet.
6. Klicken Sie auf **Importieren**, und klicken Sie dann auf **Datei wählen**. Suchen Sie die Datei **CampusDataMap.xml**, die zuvor heruntergeladen wurde, und wählen Sie sie aus. Drücken Sie dann auf **OK**. 
7. Die Datei Campus-Datenzuordnung sollte erfolgreich importiert werden. Beim Auftreten eines Fehlers navigieren Sie zurück, und überprüfen Sie, ob Sie alle erforderlichen Entitäten und Felder aus den vorherigen Aufgaben erstellt haben.
8. Wählen Sie aus dem oberen Menü **Lösungen** aus, und klicken Sie auf **Alle Anpassungen veröffentlichen**.

## Aufgabe Nr. 2: Daten importieren  

1. Laden Sie [CampusData.zip](../../Allfiles/Labs/CampusData.zip) herunter.
2. Navigieren Sie zum Power Platform Admin Center unter <https://admin.powerplatform.microsoft.com>.
3. Wählen Sie Ihre Bellows College-Umgebung aus.
4. Klicken Sie oben auf **Einstellungen**.
5. Erweitern Sie den Abschnitt **Datenverwaltung**, und wählen Sie dann **Datenimport-Assistent** aus.
6. Drücken Sie auf **DATEN IMPORTIEREN**.
7. Klicken Sie auf **Datei wählen**. Suchen Sie dann die zuvor heruntergeladene Datei **CampusData.zip**, und wählen sie aus.
8. Klicken Sie auf **Weiter** und dann erneut auf **Weiter**.
9. Wählen Sie **CampusImportDataMap** aus, und klicken Sie auf **Weiter**.
10. Überprüfen Sie die Zuordnungszusammenfassung. Klicken Sie auf **Weiter** und anschließend auf **Übermitteln**.
11. Klicken Sie auf **Fertig**.
12. Der Datenimport beginnt jetzt. Mithilfe der Schaltfläche „Aktualisieren“ auf der rechten Seite des Bildschirms **Meine Importe** können Sie jetzt die Tabelle aktualisieren, bis alle vier Importe den Statusgrund **Abgeschlossen** aufweisen. Dies kann einige Minuten dauern.

## Aufgabe Nr. 3: Datenimport überprüfen

1. Wählen Sie die Lösung **Campusmanagement** aus. Sollte make.powerapps.com noch nicht geöffnet sein, dann navigieren Sie zu make.powerapps.com, und klicken Sie im linken Bereich auf „Lösungen“, um nach Ihrer Lösung zu suchen.*
2. Wählen Sie die Entität **Besuch** aus, und wählen Sie dann die Registerkarte **Daten** aus.
3. Klicken Sie in der oberen rechten Ecke auf **Aktive Besuche**, um die Ansichtsauswahl anzuzeigen, und wählen Sie dann **Alle Felder** aus.
4. Wenn der Import erfolgreich war, sollte eine Liste der Besuchseinträge angezeigt werden.
5. Klicken Sie auf einen beliebigen Wert in der Spalte **Gebäude**, und bestätigen Sie, dass das Gebäudeformular in einem separaten Fenster geöffnet wird.
6. Klicken Sie auf einen beliebigen Wert in der Spalte **Besucher** (möglicherweise müssen Sie nach rechts scrollen), und bestätigen Sie, dass das Kontaktformular in einem separaten Fenster geöffnet wird.

# Herausforderungen

* Würden Sie in Betracht ziehen, die Terminaktivität als Teil der Lösung zu verwenden? Was würde sich ändern?
* Wie wird erzwungen, dass das geplante Ende nach dem geplanten Start liegt? 
* Fügen Sie Unterstützung für mehrere Besprechungen während eines einzelnen Besuchs hinzu.
* Schützen Sie den Gebäudezugang nicht nur für externe Kontakte, sondern auch für interne Mitarbeiter.
* Bestimmte Gebäude dürfen nur nach Genehmigung des Managements betreten werden. Was würde der Genehmigungsprozess im Datenmodell ändern?

