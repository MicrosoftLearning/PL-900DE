---
lab:
    title: 'Lab: Datenmodellierung'
    module: 'Modul 2: Einführung zu Common Data Service'
---

# Modul 2: Einführung zu Common Data Service
## Lab: Datenmodellierung


Szenario
========
    
Das Bellows College ist eine Bildungsorganisation mit mehreren Gebäuden auf dem Campus. Campusbesuche werden derzeit in papierform aufgezeichnet. Die Informationen werden nicht konsistent erfasst und es gibt keine Möglichkeit, Daten über die Besuche auf dem gesamten Campus zu sammeln und zu analysieren. 

Die Campusverwaltung möchte ihr Besucherregistrierungssystem modernisieren, wobei der Zugang zu den Gebäuden von Sicherheitspersonal kontrolliert werden soll und alle Besuche von den entsprechenden Gastgebern zuvor registriert und aufgezeichnet werden müssen.

Während dieses Kurses erstellen Sie Apps und führen eine Automatisierung durch, damit das Verwaltungs- und Sicherheitspersonal des Bellows College den Zugang zu den Gebäuden auf dem Campus verwalten und kontrollieren kann. 

In diesem Lab richten Sie eine Umgebung ein, erstellen eine Common Data Service (CDS)-Datenbank und eine Lösung, um Ihre Änderungen nachzuverfolgen. Sie erstellen auch ein Datenmodell, um die folgenden Anforderungen zu unterstützen:

-   R1 –  Verfolgen Sie Standorte (Gebäude) der Campusbesuche
-   R2 –  Aufzeichnen der grundlegenden Informationen, um die Besucher zu identifizieren und nachzuverfolgen 
-   R3 – Planen, Aufzeichnen und Verwalten von Besuchen 

Zum Abschluss importieren Sie Beispieldaten in den Common Data Service.

Weiterführende Schritte des Lab
======================

Um Ihre Lernumgebungen vorzubereiten, werden Sie:

* Eine Lösung und einen Herausgeber erstellen
* sowohl neue als auch vorhandene Komponenten hinzufügen, die zur Erfüllung der Anwendungsanforderungen erforderlich sind. Die Metadatenbeschreibung (Entitäten und Beziehungen) finden Sie im [Datenmodelldokument](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/Labs/Campus%20Management.png). Sie können die STRG-TASTE gedrückt halten oder mit der rechten Maustaste auf den Link klicken, um das Datenmodelldokument in einem neuen Fenster zu öffnen.

Nach Abschluss aller Anpassungen wird Ihre Lösung mehrere Entitäten enthalten:

-   Kontakt
-   Gebäude
-   Besuch

## Voraussetzungen:

* Keine

Vor Beginn zu beachtende Punkte:
-----------------------------------

* Namenskonvention
* Datentypen, Einschränkungen (wie etwa maximale Länge eines Namens)
* DateTime-Formatierung zur Unterstützung einer einfachen Lokalisierung

Übung 1: Umgebung und Lösung erstellen
==================================================

**Ziel:** In dieser Übung bereiten Sie die Umgebung vor und erstellen eine Lösung zur Unterstützung des Datenmodellierungsprozesses. 

Aufgabe 1: Umgebung erstellen
-----------------------------

Wenn Sie keine Umgebung besitzen und vor der Übung auch keine erhalten haben, erstellen Sie in dieser Aufgabe eine neue Arbeitsumgebung. Andernfalls können Sie mit der nächsten Aufgabe fortfahren.

1.  Melden Sie sich bei <https://aka.ms/ppac> an.

2.  Wählen Sie **Umgebungen** aus, und klicken Sie im oberen Menü auf **Neu**. Dies öffnet
    ein Menü auf der rechten Seite des Fensters.

3.  Geben Sie **Bellows College [Ihr Nachname]** als **Name** ein.

4.  Wählen Sie **Produktion** aus der Dropdown-Liste für **Typ**.

5.  Wählen Sie Ihre **Region** aus

6.  Geben Sie den **Zweck** für die Erstellung dieser Umgebung ein (optional). 
    
7.  Stellen Sie den **Umschalter** auf **Erstellen einer Datenbank für diese Umgebung** wenn Sie
    die Datenbank damit zusammen erstellen möchten, andernfalls kann dies durchgeführt werden,
    wenn die Umgebung konfiguriert ist.

8.  Klicken Sie auf **Weiter**.

9.  Wählen Sie **Sprache** und **Währung** aus. Für die Zwecke dieser Labs
    wurden für die Umgebungen **Englisch** und **US-Dollar** (USD) ausgewählt.

10. Belassen Sie **Dynamics 365-Apps** deaktiviert während Labs
    deaktiviert.

11. Belassen Sie **Beispiel-Apps und -Daten bereitstellen** während dieser Labs
    deaktiviert.

12. Klicken Sie auf **Speichern**.

13. Ihre Umgebung kann einige Minuten zur Bereitstellung benötigen. Sie können auf die Schaltfläche **Aktualisieren** klicken, um die Liste zu aktualisieren. Wenn die Umgebung bereitgestellt ist, wechselt der **Zustand** zu „Bereit“.

14. Wenn Sie Ihre Datenbank noch nicht erstellt haben, wählen Sie Ihre Umgebung aus und klicken auf **Meine Datenbank erstellen**. Andernfalls überspringen Sie diesen Schritt.

    - Wählen Sie **Währung** und **Sprache** aus. Für die Zwecke dieser Labs
    Umgebungen haben **US-Dollar** (USD) und **Englisch** ausgewählt.

    - Klicken Sie auf **Meine Datenbank erstellen**.

Aufgabe 2: Lösung und Publisher erstellen
---------------------------------------

1.  Lösung erstellen

    -   Anmelden bei <https://make.powerapps.com>

    -   Wählen Sie Ihre Umgebung aus, indem Sie in der oberen rechten Ecke des Bildschirms auf **Umgebung** klicken und Ihre Umgebung aus dem Dropdownmenü auswählen.

    -   Wählen Sie **Lösungen** aus dem linken Menü aus, und klicken Sie auf **Neue Lösung**.

    -   Geben Sie **Campusmanagement** als **Anzeigename** ein.

2.  Publisher erstellen

    -   Klicken Sie auf das Dropdown-Menü **Publisher**, und wählen Sie **+ Publisher** aus.

    -   Geben Sie in dem Fenster, das geöffnet wird, **Bellows College** als **Anzeigename** und **bc** als **Präfix** ein.

    -   Klicken Sie auf **Speichern und schließen**. 
    
    -   Klicken Sie im Popupfenster auf **Fertig**.

3.  Schließen Sie die Lösungserstellung ab.

    -   Klicken Sie nun auf die Dropdownliste **Publisher**, und wählen Sie den Herausgeber **Bellows College** aus,
        den Sie gerade erstellt haben.

    -   Bestätigen Sie, dass die **Version** auf **1.0.0.0** eingestellt ist. 
    
    -   Klicken Sie auf **Erstellen**.

Aufgabe 3: Eine vorhandene Entität hinzufügen
-----------------------------

1.  Klicken Sie zum Öffnen auf die Lösung **Campusmanagement**, die Sie gerade erstellt haben.
2.  Klicken Sie auf **Vorhandene hinzufügen**, und wählen Sie **Entität** aus.
3.  Lokalisieren Sie **Kontakt**, und wählen Sie dies aus.
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

Übung Nr. 2: Entitäten und Beziehungen erstellen
========================================

**Ziel:** In dieser Übung erstellen Sie Entitäten und fügen Beziehungen
zwischen den Entitäten hinzu.

Aufgabe Nr. 1: Entität „Gebäude“ und Felder erstellen
-----------------------------------------

1.  Sie sollten in Ihrem Browser weiterhin die Campus Management-Lösung geöffnet haben. Öffnen Sie andernfalls die Campus Management-Lösung wie folgt:
    * Melden Sie sich bei <https://make.powerapps.com> an (falls Sie noch nicht angemeldet sind)
    * Wählen Sie **Lösungen** aus, und klicken Sie zum Öffnen auf die Lösung **Campus Management**,
          zu öffnen, die Sie gerade erstellt haben.
2.  Die Entität „Gebäude“ erstellen

    -   Klicken Sie auf **Neu**, und wählen Sie **Entität** aus.
    -   Geben Sie **Gebäude** als **Anzeigename** ein. 
    -   Klicken Sie auf **Fertig**. In diesen Berichten
            die Bereitstellung der Entität im Hintergrund, während Sie mit dem Hinzufügen
            weiterer Entitäten und Felder beginnen können.

## Aufgabe 2: Erstellen der Entität „Besuch“ und von Feldern

Die Entität **Besuch** enthält Informationen zu den Campusbesuchen, einschließlich des Gebäudes, des Besuchers und des geplanten sowie des tatsächlichen Zeitpunkts jedes Besuchs. 

Wir möchten jedem Besuch eine eindeutige Nummer zuweisen, die von einem Besucher leicht eingegeben und interpretiert werden kann, wenn er beim Einchecken gefragt wird.

> [HINWEIS]
> Wir nutzen **zeitzonenunabhängiges** Verhalten beim Aufzeichnen von Datums- und Uhrzeitinformationen, da die Uhrzeit eines Besuchs *immer* die Lokalzeit am Standort des Gebäudes ist und sich nicht ändern sollte, wenn sie aus einer anderen Zeitzone angezeigt wird. 

1.  Wählen Sie die Lösung **Campus Management**
2. Entität „Besuch“ erstellen

   * Klicken Sie auf **Neu**, und wählen Sie **Entität** aus.
   * Geben Sie **Besuch** als **Anzeigename** ein 
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

Aufgabe 3: Beziehungen erstellen
------------------------------

1.  Stellen Sie sicher, dass Sie weiterhin die Entität **Besuch** der **Campus Management**-Lösung anzeigen. Navigieren Sie andernfalls dorthin.
2.  Erstellen der Beziehung „Besuch zu Kontakt“
    * Wählen Sie die Registerkarte **Beziehungen** aus.
    * Klicken Sie auf **Beziehung hinzufügen**, und wählen Sie **n:1** aus.
    * Wählen Sie **Kontakt** für **Verknüpft (Eins)** aus 
    * Geben Sie **Besucher** als **Anzeigename des Nachschlagefelds** ein 
    * Klicken Sie auf **Fertig**.
3.  Erstellen Sie die Beziehung „Besuch in Gebäude“
    * Klicken Sie auf **Beziehung hinzufügen**, und wählen Sie **n:1** aus.
    * Wählen Sie **Gebäude** für **Verknüpft (Eins)** aus 
    * Klicken Sie auf **Fertig**.
4.  Klicken Sie auf **Entität speichern**.
5.  Wählen Sie aus dem oberen Menü **Lösungen** aus, und klicken Sie auf **Alle Anpassungen veröffentlichen**.

# Übung 3: Daten importieren

**Ziel:** In dieser Übung importieren Sie Beispieldaten in die Common Data Service-Datenbank.

## Aufgabe Nr. 1: Datenzuordnung importieren

1. Laden Sie soweit noch nicht geschehen [CampusDataMap.xml](../../Allfiles/Labs/CampusDataMap.xml) herunter.
2. Navigieren Sie zum Power Platform Admin Center unter <https://admin.powerplatform.microsoft.com>, und melden Sie sich an.
3. Wählen Sie Ihre Bellows College-Umgebung aus.
4. Klicken Sie oben auf **Einstellungen**.
5. Erweitern Sie den Abschnitt **Datenverwaltung**, und wählen Sie dann **Datenzuordnungen** aus. Dadurch wird der Bildschirm „Zuordnung importieren“ auf einer neuen Browserregisterkarte geöffnet.
6. Klicken Sie auf **Importieren**, und klicken Sie dann auf **Datei wählen**. Suchen Sie die Datei **CampusDataMap.xml**, die zuvor heruntergeladen wurde, und wählen Sie sie aus, und drücken Sie dann **OK**. 
7. Die CampusDataMap-Datei sollte erfolgreich importiert werden. Wenn ein Fehler auftritt, gehen Sie zurück, und überprüfen Sie, ob Sie alle erforderlichen Entitäten und Felder aus den vorherigen Aufgaben erstellt haben.
8. Wählen Sie aus dem oberen Menü **Lösungen** aus, und klicken Sie auf **Alle Anpassungen veröffentlichen**.

## Aufgabe 2: Daten importieren  

1. Laden Sie [CampusData.zip](../../Allfiles/Labs/CampusData.zip) herunter.
2. Navigieren Sie zum Power Platform Admin Center unter <https://admin.powerplatform.microsoft.com>.
3. Wählen Sie Ihre Bellows College-Umgebung aus.
4. Klicken Sie oben auf **Einstellungen**.
5. Erweitern Sie den Abschnitt **Datenverwaltung**, und wählen Sie dann **Datenimport-Assistent** aus.
6. Drücken Sie **DATEN IMPORTIEREN**.
7. Klicken Sie auf **Datei wählen**. Suchen Sie dann die zuvor heruntergeladene Datei **CampusData.zip**, und wählen sie aus.
8. Klicken Sie auf **Weiter** und dann erneut auf **Weiter**.
9. Wählen Sie **CampusImportDataMap** aus, und klicken Sie auf **Weiter**.
10. Überprüfen Sie die Zuordnungszusammenfassung. Klicken Sie auf **Weiter** und anschließend auf **Übermitteln**.
11. Klicken Sie auf **Fertig**.
12. Der Datenimport beginnt nun. Sie können jetzt die Schaltfläche „Aktualisieren“ auf der rechten Seite des Bildschirms „Meine Importe“ verwenden, um die Tabelle zu aktualisieren, bis alle vier Importe **Abgeschlossen** als **Statusgrund** aufweisen. Dies kann einige Minuten dauern.

## Aufgabe 3: Datenimport überprüfen

1. Wählen Sie die Lösung **Campusmanagement** aus. Wenn Sie dies noch nicht geöffnet haben, navigieren Sie zu make.powerapps.com, und klicken Sie im linken Bereich auf „Lösungen“, um Ihre Lösung zu finden.*
2. Wählen Sie die Entität **Besuch** aus, und wählen Sie dann die Registerkarte **Daten** aus.
3. Klicken Sie in der oberen rechten Ecke auf **Aktive Besuche**, um die Ansichtsauswahl anzuzeigen, und wählen Sie dann **Alle Felder** aus.
4. Wenn der Import erfolgreich war, sollte eine Liste der Besuchseinträge angezeigt werden.
5. Klicken Sie auf einen beliebigen Wert in der Spalte **Gebäude**, und bestätigen Sie, dass das Gebäudeformular in einem separaten Fenster geöffnet wird.
6. Klicken Sie auf einen beliebigen Wert in der Spalte **Besucher** (möglicherweise müssen Sie nach rechts scrollen), und bestätigen Sie, dass das Kontaktformular in einem separaten Fenster geöffnet wird.

# Herausforderungen

* Würden Sie in Betracht ziehen, die *Termin*-Aktivität als Teil der Lösung zu verwenden? Was würde sich ändern?
* Wie wird erzwungen, dass das geplante Ende nach dem geplanten Start liegt? 
* Fügen Sie Unterstützung für mehrere Besprechungen während eines einzelnen Besuchs hinzu.
* Schützen Sie den Gebäudezugang nicht nur für externe Kontakte, sondern auch für interne Mitarbeiter.
* Bestimmte Gebäude dürfen nur nach Genehmigung des Managements betreten werden. Was würde der Genehmigungsprozess im Datenmodell ändern?

